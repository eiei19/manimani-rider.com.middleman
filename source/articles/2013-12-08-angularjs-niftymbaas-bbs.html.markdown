---
title: AngularJSとnifty cloud mobile backendで作る掲示板っぽいもの
date: 2013-12-08
tags: tech
description: Angularjsとnifty cloud mobile backendを使って掲示板っぽいものを作りました。ソースの公開と解説。
keywords: anjularjs,nifty,mbaas,cloud,javascript
---

<div class="image-wrapper">
<a href="http://500px.com/photo/54246890">
  <img class="header" src="http://ppcdn.500px.org/54246890/5b9e8cb3080501deea56893d37d0c1b817b5d346/4.jpg" alt="Untitled by Akihiro Nagashima on 500px.com" border="0" style="margin: 0 0 5px 0;" width="800px">
</a>
</div>

xin chào!!

相変わらずハノイからコンニチハですが、今日はベトナムとまったく関係のないことについて書きます。

題して、AngularJSとnifty cloud mobile backendで作る掲示板っぽいもの、ってことでちょっと作ってみました。

とりあえずいろいろ前置き書くけど、そんなんいらねって人は一気にソースまでとんでね。

下へ下へ。

## とても長い前置き

### javascriptの実装をいい感じにしたいぜ、jQueryは限界だ

今自分がやってるプロジェクトでは当然javascriptの実装がもりもりあります。

jQueryはとても良いライブラリだけど、処理が増えてくると正直しんどいものがある。

使うのが新人（自分も大して変わらないが）だったりするとソースが地獄絵図に。

jQuery地獄。

### javascriptにもフレームワークを

サーバーサイドにはRailsだのfuelだのいろいろあるじゃないか。

なんでクライアントサイドはjQueryで戦い続けてるんだ。

ってことで、javascriptにもフレームワークを入れたいと思った。

### AngularJSいいよAngularJS

で、なんか知らんけど流行ってるじゃね？

ってことでBackboneとAngularJSをいじってみたんだけど、正直Backboneはちょっと。。。

や、自分がバカなだけかもしれないんですけど、バカでごめんね、AngularJSのほうがなんか好き。

というわけでAngularJSを採用することにした。

### AngularJSとは

googleが作ってるJSのMVCフレームワーク。

<a href="http://angularjs.org/" target="_blank">AngularJS — Superheroic JavaScript MVW Framework</a>

英語がダメな人は日本語もあるよ。

<a href="http://js.studio-kingdom.com/angularjs" target="_blank">AngularJS 1.2 日本語リファレンス ｜ js STUDIO</a>

ところどころ抜けてるけど。

日本語で目次とか段落を見て大事そうなところを本家読むってのが効率いい気がする。

ドキュメントはちゃんと読もう。

ドキュメントに非推奨パターンって書いてあるのにそのままのサンプルをWeb上でいっぱい見た。

コピペでも動くけどフレームワークを効果的に使うにはコンセプトの理解が不可欠やで。

### 簡単なアプリを書いてみる

実はAngularJSはメンバーに実際のプロダクトで使ってもらってる。

でも、悲しいことに自分はもうコードを書かせてもらえないので、ちょっと簡単なのを書いてみる。

### ただ書くだけじゃつまんないからmBaaSとか使ってみる。

今！はやりの！

うちの会社（ニフティだよ！）が出してるmBaaSがあるのでそれを使ってみる。

nifty cloud mobilebackendというやつですね。

### nifty cloud mobilebackendとは

これです。

<a href="http://mb.cloud.nifty.com/" target="_blank">アプリ開発をよりスマートに、スピーディに ｜ ニフティクラウド mobile backend</a>

mBaaSはけっこういろいろとあると思うのだけどシンプルでいいかと。

この前titaniumのcloud（<a href="http://www.appcelerator.com/cloud/" target="_blank">これ</a>）をスマホアプリ開発で使ったことがあったのだけどイマイチだった。

## 実装

こっからが本番です。こっからが本番です。

大事なことなので(ry。こっからが本番です。

### DEMO

まあ、まず<a href="http://mnrider.me/18tQUh8" target="_blank">DEMO</a>をどうぞ。

### ソースコード

<a href="http://mnrider.me/18tRqM4" target="_blank">github</a>です。見てください。

### 解説が要りそうなところ

51行の目の angular.element('#Posts').scope() はcontrollerのスコープ外から$scopeを参照する方法。

あとrefresh関数の中ではdeferredを使ってます。

リクエストは1つだし使う必要はまったくないのだけど試しに。

deferredは今さらちゃんとわかった。とても便利！！

deferredの参考文献は下記。

* <a href="http://qiita.com/yuku_t/items/3d1cf51d7ae91305eaaa" target="_blank">JavaScript - jQuery.Deferredを使って楽しい非同期生活を送る方法 - Qiita [キータ]</a>
* <a href="http://tkawachi.github.io/blog/2013/01/06/jquery-deferred/" target="_blank">jQueryのDeferredとPromise - tkawachi Blog</a>
* <a href="http://d.hatena.ne.jp/hokaccha/20130914/1379136976" target="_blank">AngularJSのdeferredで並列実行 - hokaccha.hamalog v2</a>

app.jsだけ貼っておきます。

<script src="https://gist.github.com/eiei19/a81f18206aaa8605ca6f.js"></script>

## まとめ

AngularJSすげーいいですね。

あとmBaaSが意外と便利。

Webサービスなんて取ってきて表示するだけなので簡単なサービスだったらこれで足りてしまいそうですね。

以上です(｀ー´)ノ