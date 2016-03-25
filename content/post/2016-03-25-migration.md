---
title: 'スタッフブログを静的サイトに移行しました'
author: tamaoki
layout: post
date: 2016-03-25
banner: images/2016/03/migration-450x250.png
archives:
  - 2016
  - 2016/03
  - 2016/03/25
url: /2016/03/25/migration
categories:
  - 全般
  - 静的サイトジェネレータ
  - Hugo
---

久しぶりの投稿になります、 tamaoki ([@t0shiya](https://twitter.com/t0shiya)) です。

[2014年4月の開設](/2014/04/18/45/) からずっと [WordPress](https://ja.wordpress.org/) で運用していた本スタッフブログを静的サイトに移行しました。

昨年末から弊社が管理しているウェブサイトを徐々に静的サイトに移行していて、これで既に６サイト目。今回も静的サイトジェネレータ [Hugo](http://gohugo.io/) を使用しています。  

既存のテーマを拝借して、[WordPress](https://ja.wordpress.org/) から記事をエクスポートしたり何やかんや手を入れてトータル３日くらいで設置しました。その後も少しずつ修正してますが。
ちなみに本サイトは [GitHub Pages](https://pages.github.com/) で運用。ソースコードも [弊社のGitHub](https://github.com/feedtailor/StaffBlog) で公開しています。

というわけで、構築した時のノウハウとか課題とか、本サイトを更新しながら備忘録的に書いていく予定です。静的Webサイトに関する勉強会もやってますので、興味のある方は是非ご参加ください。

* [第2回 静的Webサイト 勉強会](http://connpass.com/event/26420/)
* [第1回 静的Webサイト 勉強会](http://connpass.com/event/25507/)

静的サイトへの移行については「なんでそんな面倒臭いことを？」とか「わざわざ移行する必要ある？」とか意見はあると思いますが、好きなテキストエディタを使って [Markdown記法](https://daringfireball.net/projects/markdown/) で書けるので個人的にはとても気に入ってます。

もちろん動的サイトじゃないと無理って言うところもあるので、全部置き換えることはできないしその必要もありませんが、Markdownで記事を書いてサクッと投稿、みたいな運用をしたい方は移行を検討してみても良いのではないでしょうか。
