---
title: 新しいライフログサービス Dailyshot の ver1.1.0 を公開しました
author: すみひろ
layout: post
date: 2014-11-17
banner: http://feedtailor.jp/staff/wp-content/uploads/2014/11/dailyshot_logo_100.png
archives:
  - 2014/11
  - 2014/11/17
url: /2014/11/17/613
categories:
  - アプリご紹介
tags:
  - Dailyshot

---
[すみひろ](http://twitter.com/sumihiro)です。Dailyshotに投稿するために肉のネタを探し回る毎日です。ウラナンバにはいい店が多いですね。

先日、 [新サービス Dailyshot をリリース](http://feedtailor.jp/staff/2014/11/05/565) しましたが、本日はその Dailyshot のアップデート v1.1.0 のご紹介です。

あ、ご紹介が遅れました。 Dailyshot は企画とサーバ側を [くまくら](http://twitter.com/kumatch) が担当し、クライアントは私 [すみひろ](http://twitter.com/sumihiro) が担当しています。

Dailyshot のダウンロードはこちらから。
  
<a href="https://itunes.apple.com/jp/app/dailyshot/id932716879" target="_blank"><img src="http://feedtailor.jp/staff/wp-content/uploads/2014/04/Download_on_the_App_Store_Badge_JP_135x40_1004.png" alt="AppStoreからダウンロード" width="135" height="40" class="alignnone size-full wp-image-58" /></a>

## アップデートの内容

今回のアップデートの内容は以下の通りです。

  * カラムの呼び方をテーマに変更 
  * ショットをシェアできるようになりました。ショットをTwitterやFacebbokに投稿することができます 
  * テーマのタイトルが変更できるようになりました 
  * テーマの削除時に確認が入るようになりました 
  * 利用規約とプライバシーポリシーへのショートカットを追加しました 
  * iPodで流れている曲をそのまま流したままにできるようになりました 
  * 受け取る通知を選択できるようになりました 
  * URLスキームが追加されました。 &#8220;dailyshot://shot/[テーマID]/[ショットID]&#8221; でショットを外部から表示させることができます。例えばこのようなURLを使用します。 dailyshot://shot/1433449752001009/12991889726942045 
  * サービスにそぐわないショットを運営に報告できるようになりました 
  * 特定のユーザーのテーマがパブリックタイムラインに表示されないようにブロックできるようになりました 
  * その他、多くの不具合の修正

いくつかピックアップして、詳しくご紹介します。

<!--more-->

## カラムの呼び方をテーマに変更

Dailyshot は表計算ソフトのように行と列で構成されています。
  
行と列の組み合わせを「タイムライン」、それぞれの列を「カラム」と呼んでいましたが、今回のバージョンより「カラム」は「テーマ」という呼び方に変更されました。
  
機能的には変化はありませんが、一続きの写真を「テーマ」と呼ぶことによってより親しみが湧くのではないでしょうか。

## ショットをシェアできるようになりました。ショットをTwitterやFacebbokに投稿することができます

今まではあまり表に出ていませんでしたが、 Dailyshot はブラウザから見ることもできます。
  
例えば、私のショットはこのページで見ることができました。
  
<http://dailyshot.me/sumihiro>
  
見事に食欲の塊ですね。

今回のアップデートでは Twitter や Facebook にショットをシェアすることができるようになりました。
  
使い方は簡単。シェアしたいショットを表示させ、「シェア」ボタンを押せばシェアする方法を選ぶことができます。

[<img src="http://feedtailor.jp/staff/wp-content/uploads/2014/11/IMG_3064-300x266.jpg" alt="IMG_3064" width="300" height="266" class="alignnone size-medium wp-image-620" />](http://feedtailor.jp/staff/wp-content/uploads/2014/11/IMG_3064.jpg)

Twitter や Facebook にシェアする場合には iOS の設定でそれぞれのアカウントの設定が必要ですのでご注意くださいね。

## 受け取る通知を選択できるようになりました

Dailyshot は「フォローしているユーザーがショットを投稿した時」と「自分のショットにLikeがついた時」に通知を行います。
  
1日に1個しかショットを投稿できない Dailyshot で友達のショットを見逃さないように通知が行われますが、時には煩わしいこともあります。
  
そのような時には通知をオフにしてしまうことが可能になりました。

また、「新しいショットはすぐには見なくてもいいけど、Likeされた時はすぐに知りたい！」にも対応します。
  
「フォローしているユーザーがショットを投稿した時」と「自分のショットにLikeがついた時」の通知をそれぞれ別にオンオフの設定ができますので、必要に応じて使い分けましょう。

[<img src="http://feedtailor.jp/staff/wp-content/uploads/2014/11/IMG_3067-300x266.jpg" alt="IMG_3067" width="300" height="266" class="alignnone size-medium wp-image-621" />](http://feedtailor.jp/staff/wp-content/uploads/2014/11/IMG_3067.jpg)

お詫び： v1.1.0 現在、通知の設定を表示した時に、すでに設定されたされた状態ではなく両方ともオフで表示されてしまう不具合が確認されています。次のリリースで修正される予定です。表示がオフになっていても、最後にオンに設定した状態では通知は正しく行われます。

## URLスキームが追加されました。 &#8220;dailyshot://shot/[テーマID]/[ショットID]&#8221; でショットを外部から表示させることができます。

一部のユーザーさんに熱望される URL スキームに対応しました。
  
例えばこのようなURLを使用します。

> dailyshot://shot/1433449752001009/12991889726942045

今回は「ショットを表示する URL スキーム」のみの対応ですが「ユーザーのタイムラインを表示する URL スキーム」も今後のアップデートで対応する予定です。

## サービスにそぐわないショットを運営に報告できるようになりました

## 特定のユーザーのテーマがパブリックタイムラインに表示されないようにブロックできるようになりました

Dailyshot では [利用規約](http://dailyshot.me/legal/terms.html) の第9条 (禁止事項)にていくつかの行為を禁止しています。
  
禁止されている投稿を見かけられた場合は運営に報告をお願いいたします。
  
また、禁止されている投稿ではなくとも、ご自身が見たくない投稿を行っているユーザーをブロックすることも可能になりました。
  
ブロックすると、そのユーザーの投稿がパブリックタイムラインに流れてこなくなります。ただし、ブロックしたユーザーがご自身のショットを見ることは引き続き可能です。

### 最後に

「報告」と「ブロック」の機能ですが、実は Apple の新しいレビューガイドラインの 14.3 項にて実装が必要とされている機能です。
  
この機能のために何度かリジェクトを受けてしまったためにアップデートのリリースが遅れてしまいました。
  
該当するサービスを運営する方はご注意を。

<a herf="http://feedtailor.jp/staff/2014/11/17/627">14.3項のリジェクトに対応する方法</a>を別記事でご用意しています。
  
Dailyshot のダウンロードはこちらから。
  
<a href="https://itunes.apple.com/jp/app/dailyshot/id932716879" target="_blank"><img src="http://feedtailor.jp/staff/wp-content/uploads/2014/04/Download_on_the_App_Store_Badge_JP_135x40_1004.png" alt="AppStoreからダウンロード" width="135" height="40" class="alignnone size-full wp-image-58" /></a>