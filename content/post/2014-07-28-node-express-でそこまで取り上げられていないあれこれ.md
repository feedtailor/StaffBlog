---
title: Node Express でそこまで取り上げられていないあれこれ
author: kumakura
layout: post
date: 2014-07-28
banner: images/2014/07/express-450x141.png
archives:
  - 2014/07
  - 2014/07/28
url: /2014/07/28/267
categories:
  - Node
  - 技術情報
tags:
  - Express
  - Node

---
くまくらです。

私は API サーバを実装する際に Node の Express を利用する事が多いので、今回は使っていて知った事のうち、世間的にはポツポツ程度にしか取り上げられていない事柄をいくつかあげていきます。簡単に Express を利用している初心者レベルを主な対象としています。

## 前置き

以後の文中にて登場する名称／変数値は、[Express API リファレンス](http://expressjs.com/4x/api.html) を始めとした各種ドキュメント内でも扱われているものと同等に、以下のインスタンスを指すこととします。

  * app: Application インスタンス
  * req: Request インスタンス
  * res: Response インスタンス
  * routes: Application インスタンスによるURLルート定義にてマッピングされた Middleware

## app, req, res のライフサイクルについて

本当に基本的なことですが、Express による Web アプリケーションの根幹となる app インスタンスは、インスタンス作成時から各種セットアップ、サーバ Listen を行い始めた後も永続し、Listen を終了（Express アプリケーションを終了）させるまでは残り続けます。
  
一方、Middleware の引数として用いられる req, res の両インスタンスは、クライアントからのリクエストを受信し処理を開始した時点で生成、初期化され、Middleware による遷移処理が終了したあとに消滅します。

以上のことから、app インスタンスは Web アプリケーション全体に関わるグローバル／汎用的な情報を保持すること、req, res インスタンスはクライアント固有の情報を保持する存在である捉えたほうがよさそうです。従って app インスタンスは Listen 時点ではもう情報が完成しており、req, res インスタンスはリクエスト受信時から応答結果を返すまで如何様にも情報操作を行うことができる対象であると言えます。

## app.request, app.response

req, res の両インスタンスは最初の Middleware へ与えられる直前（厳密には内部で実行される最初の暗黙の Middleware で）app.request, app.response を prototype として設定されます。この app.request, app.response はそれぞれ Express モジュールが提供する Request, Response インスタンスを prototype とするオブジェクトです。

app.request, app.response 共に app インスタンスを生成した時点で用意されるため、例えば Web アプリケーション固有のリクエスト処理やレスポンス処理をメンバ関数に定義しておけば、Middleware、あるいは routes でそれらを利用することができます。

<pre>var app = express();

app.request.getAwesomeHeader = function () {
    return this.headers[‘x-awesome'] || null;
};
</pre>

## 任意の値に Middleware でアクセスしたい話

Express を利用しはじめた人が行き当たる話で、任意の値（変数）を Middleware、特に routes 以下で利用するにはどうすればよいかというのものがあります。例えば app インスタンスの set() した値を参照したい、あるいは app.js で作成した値を routes 以下で参照したいなどです。基本的には好きなようにやってよいと思っていますので、いくつかの手段を紹介します。用途あるいは好みとしてフィットする方法を選んで使ってみてください。

### 1. req.app, res.app

実は req, res それぞれは app インスタンスをメンバとして保持していますので、それを利用することができます。

<pre>exports.view = function (req, res) {
    var app = req.app;
    var title = app.get("title");
    // ....
};
</pre>

### 2. 前面にある Middleware で仕込む

利用したい値を比較的早い段階の Middleware で req などに予め設定しておきます。前述したように req インスタンスはリクエスト毎のライフサイクルを持っているので、リクエストクライアント固有の情報などを扱う場合はこちらの方法がよさそうです。

<pre>app.use( function (req, res, next) {
    req.domains = {
        flow : “awesome"
    }
});
app.use("/users", routes.users);
</pre>

### 3. Middleware / routes 作成時の引数として任意の変数を与える

Middleware, routes の実装時、それらを作成する関数として exports する体制にしておけば、require() 時に引数を与えてインスタンスを作成しつつ、Middleware 側で与えられた引数を用いた処理ができるようになります。

_routes/items.js_

<pre>module.exports = function (services) {
    return {
        index: function (req, res, next) {
           if (services.is_awesome) {
               res.send(200, “Success !!”);
           }
        }
    };
}
</pre>

_app.js_

<pre>app.use(“/items”, require(“./routes/items”)(services));
</pre>

## view のキャッシュについて

Production 環境で稼働している、あるいは res.render() のオプションに cache = true を付与することで、view に対してキャッシュが有効となりますが、これはレンダリング処理に関わる各種情報のキャッシュであり、ページキャッシュではありません。

Express で HTML ページをレンダリングするシチュエーションは大抵動的ページになると思いますが、ほんの僅かな時間でもページキャッシュをして処理を軽くしたいケースはありそうです。res.render() の第３引数にコールバック関数を設定すれば HTML ページの実体が得られるので、これを利用することでページキャッシュの振る舞いを自前で用意することができます。なお res.render() にコールバック関数を与えるとクライアントへの送出処理が省略されるため、自分で res.send() する必要があります。

<pre>var caches = {};  // ※ Middleware スコープ外


/// 注釈, 以下 middleware 内の処理

if (caches[id]) {
    res.send(caches[id]);
} else {
    res.render(“view.jade”, values, function (err, content) {
        if (err) {
            next(err);
        } else {
            caches[id] = content;
            res.send(content);
        }
    });
}
</pre>

## おまけ: routes 以下に設置したファイルの読み込みを楽にする

Express 固有の話ではありませんが、いくつかの routes 定義ファイルを１つずつ require() していくのは若干面倒です。そこで [require-directory](https://github.com/troygoode/node-require-directory) モジュールを利用すると、指定するディレクトリ以下にある全てのファイルを１つのオブジェクトへまとめて exports オブジェクトへ再帰的にマッピングしてくれるため、ルーティング定義時が少し楽になります。

_routes/index.js_

<pre>var requireDirectory = require('require-directory');
module.exports = requireDirectory(module);
</pre>

_app.js_

<pre>var routes = require('./routes');

app.use('/users',    routes.users);
app.use('/blogs',    routes.blogs);
app.use('/login',    routes.auth.login);
app.use('/register', routes.auth.register);
</pre>