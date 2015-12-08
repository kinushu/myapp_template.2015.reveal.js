# 自分用Webアプリ雛形まとめ 2015

2015/12/08(tue)

shuhei kinukawa (@kinushu)

---

### reveal.js使用もこなれてきた。

+ github の gh-pages ブランチで手軽にweb公開。
+ kobito でプレビューしながら記入、reveal.jsに流し込み。

---

* 最近自分用Webアプリモックを作ってみている。
* ここら辺がきっかけ。

昨今の自分用Webアプリケーションひな形
http://d.hatena.ne.jp/naoya/20130503/1367581629
https://github.com/naoya/boilerplate

* slim, sass, CoffeeScript, npm などを使用している。


---

### 効用

* 自分用のよくやることを最初からまとめておける。
* 結果的に今使われているライブラリを納得して使えるようになった。
* ある案件でやったカスタマイズの汎用化がしやすくなった。

---

### 使おうとなった gem

+ sinatra w/ reloader
+ erb
+ activerecord
+ sass
+ livereload w/ guard
+ rspec

---

### railsでなくsinatraがよい

* ルーティングを考える際に、railsだとどうしてもmodel=DBテーブルとなる。
* 重い…
* rootingを柔軟に考えるならsinatraの方が組み易い（今のところ）

---

### sass(利点)

+ scssを利用 (css + α として使える。)
+ 変数が使える -> DRY!
+ 継承構造をネストで書ける -> DRY!
+ mixin, include で属性共通使用できる -> DRY!
+ 他いろいろ

---

### sass(使い方)

+ レンダリング時にscss->css変換を実施
    * cssファイルの生成を抑えられる（というのをメリットとする
+ 製作時にscss->css変換し、cssファイルを配置
    * 従来フローに加え易い

---

### 自動更新はとても便利

+ guard 内で以下が動いている
    * sass (.scssファイルが更新されたら .cssにコンパイル)
    * shotgun (.rb が更新されたらwebサーバ再起動相当)
    * livereload (ブラウザリロード)
+ エディタで書く→ブラウザをリロードする、という手順が一つ減るだけで楽

---

### readme 書くの重要

+ 1プロダクトとしてまとめやすくなる
+ テンプレートを設定して、埋めていく意識だと作り易い

http://deeeet.com/writing/2014/07/31/readme/

   + Overview, Description, Usage, Install など書きたい

+ 使用する際の入力、前提条件が明確になる（重要）
+ Xヶ月後に見ても（すぐに）思い出せる

---

### (枠外)管理画面の作り方（検証中）

##### railsでも管理画面作れる？

+ rails_admin

http://rails-admin-tb.herokuapp.com/

+ active_admin

http://demo.activeadmin.info/admin

##### sinatra(padrino)でも管理画面が簡単に作れる?

```
padrino g admin
```

* relationが複雑なのはあまり期待しない

---

ご静聴ありがとうございました。
