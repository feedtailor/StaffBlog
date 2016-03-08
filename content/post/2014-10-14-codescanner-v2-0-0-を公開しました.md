---
title: CodeScanner v2.0.0 を公開しました
author: itok
layout: post
date: 2014-10-14
banner: /images/2014/10/iTunesArtwork2-450x200.png
archives:
  - 2014/10
  - 2014/10/14
url: /2014/10/14/501
categories:
  - アプリご紹介
tags:
  - CodeScanner
  - アプリリリース

---
<a href="https://itunes.apple.com/app/id352276408" target="blank"><img src="/images/2014/10/3a32a3262646918bc6b4c57662b6c293.png" alt="Icon-60@2x" width="120" height="120" class="alignnone size-full wp-image-502" /></a>

またまた1年半ぶりに更新したアプリの紹介です。

#### 更新内容

  * iOS7/8対応
  
    * iOS7以降のみの対応となります
  * デコードをiOS標準ライブラリに置き換え（1/2次元の切り替えを廃止）
  * ネットワーク連携を廃止
  * 対応ブラウザの整理

<a href="https://itunes.apple.com/app/id352276408" target="blank"><img src="/images/2014/04/Download_on_the_App_Store_Badge_JP_135x40_1004.png" alt="AppStoreからダウンロード" width="135" height="40" class="alignnone size-full wp-image-58" /></a>

前バージョンまでは1/2次元のコード読み取りにZxingというオープンソースのライブラリを使用していたのですが、iOS7よりOS標準で対応しましたので、全面的に差し替えました。

対応コードはOSの仕様に準じますが、いまのところ以下の通りです。

  * 1次元 
      * UPC-E
      * EAN-8, EAN-13
      * CODE 39
      * CODE 93
      * CODE 128
      * ITF
      * PDF417
      * Interleaved 2 of 5
  * 2次元 
      * QR Code
      * Data Matrix
      * Aztec

* * *

### 簡単なアプリ紹介

さて、久しぶりのアップデートなのでざっくりとですがアプリの紹介も。

> CodeScannerはバーコードやQRコードをはじめとする 1次元 or 2次元コードを連続して読み取る事のできるリーダーアプリです。

ということで、よくあるコードリーダーなのですが、**連続して読み取る事のできる**というところがキモになっております。

起動すると、スキャン画面です。シャッターボタンとかはないので、カメラに写ったコードを片っ端からどんどん読み込んでいきます。一番下に表示されているのが、直近の読み取り結果になります。

[<img src="/images/2014/10/20141014_1.png" alt="20141014_1" width="338" height="600" class="alignnone size-full wp-image-505" />](/images/2014/10/20141014_1.png)

スキャン履歴一覧です。読み込んだコードに応じた処理がいろいろできます。複数の読み込み結果を連結してコピー、なんてこともできます。

[<img src="/images/2014/10/20141014_2.png" alt="20141014_2" width="338" height="600" class="alignnone size-full wp-image-506" />](/images/2014/10/20141014_2.png)

たとえば、読み込んだコードがURLならブラウザを開きます。Safari以外のブラウザアプリが入っている場合も設定次第で、直接呼び出せるようになります。

[<img src="/images/2014/10/20141014_3.png" alt="20141014_3" width="338" height="600" class="alignnone size-full wp-image-507" />](/images/2014/10/20141014_3.png)

ほかにも、住所登録や電話はもちろん、バーコードからアマゾン・Googleショッピングへのアクセスも可能です。

* * *

あるとなにかと便利なコードリーダー。是非使ってみてください。

<a href="https://itunes.apple.com/app/id352276408" target="blank"><img src="/images/2014/04/Download_on_the_App_Store_Badge_JP_135x40_1004.png" alt="AppStoreからダウンロード" width="135" height="40" class="alignnone size-full wp-image-58" /></a>