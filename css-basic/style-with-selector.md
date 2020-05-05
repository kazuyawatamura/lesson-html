# CSSセレクターについて

CSSによるデザイン指定をどのHTML要素に適用させるかを指定するのに用いられるのが「CSSセレクタ」です。


## 代表的なセレクター一覧



### インラインStyle属性

```html
<p style="color: red;">インラインスタイル</p>
```



### タグセレクター

HTMLにスタイルを充てる方法です。



#### `<p>` タグの文字色を赤にしてください。

```html
<p>pタグの内容</p>
<span>spanタグの内容</span>
```

```css
p {
  color: red;
}
```
![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-selector1.png)



### クラスセレクター

タグセレクターのようにHTMLタグを直接指定すると

* 複数ページ、複数パーツに渡って
* 同じタグに
* 同じスタイルが適用

されてしまいます。  
意図する場所だけにスタイルを充てるためにクラスセレクターを使うクセを付けておきましょう。  
（場合に応じてタグセレクターを使用することもあります）



#### `hello-wrapper` クラスがついた要素の文字色をオレンジ色にしてください。

```html
<p class="hello-wrapper">pタグの内容</p>
<span>spanタグの内容</span>
```

```css
.hello-wrapper {
  color: orange;
}
```


### 複数一括セレクター
「,」（カンマ）でクラスを繋いで複数のクラスにスタイルを適用する事ができます。



#### `.goodbye` クラスと`.hello`クラスが付いた要素の文字色をグレーにしてください。

```html
<p class="goodbye">pタグの内容</p>
<span class="hello">spanタグの内容</span>
```

```css
.goodbye, .hello {
  color: gray;
}
```


### 子孫セレクター

もっともよく見かけるセレクターの種類です。  
HTMLタグの入れ子をした状態で細かく指定できることが大きなメリットです。



#### `.hello-wrapper` クラスの子要素の `.hello`クラスが付いた要素の文字色をグリーンにしてください。

```html
<div class="hello-wrapper">
  <p class="goodbye">pタグの内容</p>
  <span class="hello">spanタグの内容</span>
</div>
```

```css
.hello-wrapper .hello {
  color: green;
}
```


### IDセレクター

今までのクラスセレクターは、```class="xxx"``` や ```.xxx``` で記述していましたが、IDセレクターは若干違います。  
クラスセレクターとの違いは同じID名を他のタグでは使うことはできません。  
そのためクラスセレクターと違って使い勝手が悪いのでIDセレクターはあまり使いません。  
（筆者はJavaScriptのセレクターとして使用することが稀にあります）



### ```id-selector```のIDが付いた要素の文字色を水色にしてください。

```html
<div id="id-selector">IDセレクタで文字の色を変える</div>

<!-- 2回目のこのIDセレクターは使用不可 -->
<div id="id-selector">IDセレクタで文字の大きさを変える</div>
```

```css
#id-selector {
  color: skyblue;
}
```

※ id名は同じ要素に対して複数のid名を指定することはできません。
```html
<div id="test test2">これは無効です</div>
```



### ユニバーサルセレクター（全称セレクター）

すべてのHTML要素を対象に共通のCSSプロパティを指定したい場合のプロパティです。

```css
* {
　color: blue;
}
```



### 書いて覚えよう

上述した
* インラインStyle属性
* タグセレクター
* クラスセレクター
* 複数一括セレクター
* 子孫セレクター
* IDセレクター

を用いて自由にスタイルを設定してみてください。


```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>セレクタの練習</title>
    <style>
    　/* ここにスタイルシートを書く */
    </style>
  </head>
  <body>
    <div>
      <p class="hello">こんにちは</p>
    </div>
    
    <p style="color: pink;">こんばんは</p>

    <p id="id-selector">はじめまして</p>

    <p class="goodbye">さようなら</p>

    <div class="hello-wrapper">
      <div class="hello">こんにちは</div>
    </div>
  </body>
</html>
```


## クラスの付け方のルールや注意点

クラスセレクターを利用する際にルールや注意点があります。

- 英字大文字小文字は区別される。
- 日本語もOK（だけど使わない）
- 使用できる記号は「-」ハイフンと「_」アンダーバー
- 数字もOKだが、頭にはNG

```css
.hello {...}
.Hello {...}

.こんにちは {...}

.hello-goodbye {...}
.hello_goodbye {...}

.hello8 {...}
.8hello {...} /* NG */
```




## 他にもあるセレクター（selector2.html）

下記のHTMLを用意して、それぞれのCSSを試してみましょう。

```html
<section class="news-area">
  <ul class="news-area-main">
    <li>メインニュース1</li>
    <li>メインニュース2</li>
    <li>メインニュース3</li>
  </ul>
  <div>
    <ul class="news-area-sub">
      <li>サブニュース1</li>
      <li>サブニュース2</li>
      <li>サブニュース3</li>
    </ul>
  </div>
</section>
```


### 8. 子セレクター

「メインニュース1〜3だけ」を水色にする設定をしてみましょう。  
下記の「よくない例」ですとサブニュース1~3も水色になってしまいます。

`>` を利用することによって、`.news-area` の直ぐ下層にある `<ul>` の中の `<li>` という指定方法になります。

```css
/* よくない例 */
.news-area ul li {
  color: #skyblue;
}

.news-area > ul li {
  color: #skyblue;
}
```


### 9. 隣接セレクター

下記のコードの結果、メインニュース2と3の文字がピンクになります。

`<li>` を `+` で繋げることによって2番目の `<li>` を指定するようになります。


```css
.news-area .news-area-main li + li {
  background-color: pink;
}
```

例として、2番目のナビゲーションから左側に `margin-left: 10px;` を適用させたイメージです。  
すべてのナビゲーションの左側に `margin-left: 10px;` させてしまうと一番左側にも10pxの余白ができてしまってデザイン通りにはならないと思います。  
そういった時にこのテクニックは有効です。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-selector2.png)



## まだまだあるセレクター（selector3.html）

まずこちらのHTMLを用意してください。

```html
<ul class="main-menu">
  <li><a href="#">メニュー1</a></li>
  <li><a href="#">メニュー2</a></li>
  <li><a href="#">メニュー3</a></li>
  <li><a href="#">メニュー4</a></li>
  <li><a href="#">メニュー5</a></li>
  <li><a href="#">メニュー6</a></li>
  <li><a href="#">メニュー7</a></li>
  <li><a href="#">メニュー8</a></li>
  <li><a href="#">メニュー9</a></li>
  <li><a href="#">メニュー10</a></li>
  <li><a href="#">メニュー11</a></li>
</ul>
```



### 10. 擬似クラス

擬似クラスには、いろいろな種類があります。
急いですべて覚える必要はないので、こういう種類があるとだけ覚えておいてください。

- hover　　　　　 → カーソルが乗っている要素


- first-of-type　　　 → 要素内の最初の子要素
    - ■□□□□□□□□
- last-of-type　　　 → 要素内の最後の子要素
    - □□□□□□□□■
- nth-of-type(n)　　 → 要素内のn番目の子要素
    - □□■□□□□□
- nth-of-type(odd)　→ 要素内の奇数の子要素
    - ■□■□■□■□
- nth-of-type(even)  → 要素内の偶数の子要素
    - □■□■□■□■
- nth-of-type(n + 5) → 5個目以降のliを指定する場合
    - □□□□■■■■
- nth-of-type(-n + 5) → 5個目までを指定する場合
    - ■■■■■□□□


```css
/* カーソルが乗っている要素 */
.main-menu li a:hover {
  background-color: red;
  text-decoration: none;
}

/* 最初の要素 */
.main-menu li:first-of-type {
  background-color:#faa;
}
/* n番目の要素 */
.main-menu li:nth-of-type(2), .main-menu li:nth-of-type(3) {
  background-color:#afa;
}
/* 最後の要素 */
.main-menu li:last-of-type {
  background-color: #aaf;
}
/* 奇数の要素 */
.main-menu li:nth-of-type(odd) {
  background-color:#faf;
}
/* 偶数の要素 */
.main-menu li:nth-of-type(even) {
  background-color:#ffa;
}
/* 3の倍数の要素 */
.main-menu li:nth-of-type(3n) {
  background-color:#aff;
}
/* 3の倍数プラス1の要素 */
.main-menu li:nth-of-type(3n+1) {
  background-color:#aff;
}
```


#### hover について

要素の上にマウスのポインタを要素の上に置いたときに実行されるクラスです。  
リンクを作成するaタグと一緒に使われることが多い擬似クラスです。

```html
<a class="button" href=#>Button</a>
```

```css
.button {
	color: #fff;
	background-color: #3a3a3a;
	text-decoration: none;
	padding: 20px;
}
.button:hover{
  color: #000;
  background-color: #c9c9c9;
}
```



#### こちらのサイトにコードを用意したので参考にご覧ください。
https://codepen.io/cotton/pen/WNNQJqm

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="result" data-user="cotton" data-slug-hash="WNNQJqm" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="擬似クラスリファレンス">
  <span>See the Pen <a href="https://codepen.io/cotton/pen/WNNQJqm">
  擬似クラスリファレンス</a> by cotton (<a href="https://codepen.io/cotton">@cotton</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

#### 擬似クラスを試せるWebサービス
[nth-childジェネレーター](http://www.bad-company.jp/nth-child/)



## 詳細度

セレクターには詳細度というものがあり、セレクターの設定によって詳細度が変化し、セレクターの詳細度によって優先されるスタイルが上書きされます。

```html
<div>
  <p class="menu">こんにちは</p>
</div>
```
```css
div .menu {
  color: orange;
}
div p {
  color: skyblue;
}
p {
  color: palegreen;
}
```


### 点数

| **指定方法**   | **例**                  | **点数** |
| ---------- | ---------------------- | ------ |
| タグのstyle属性 | style="color: orange;" | 1000点  |
| ID         | ＃hoge                  | 100点   |
| クラス        | .hoge                  | 10点    |
| 要素名        | ul                     | 1点     |
| 擬似クラス      | :first-child           | 1点     |
| 全称セレクター     | *                      | 0点     |



### 計算例

| **例**             | **計算**                               | **合計点** |
| ----------------- | ------------------------------------ | ------- |
| style=""          | 1000（style属性）                       | 1000点   |
| ＃hoge             | 100（ID属性）                           | 100点    |
| li.color.label    | 1（要素名）+ 10（クラス属性）+ 10（クラス属性）      | 21点     |
| table tr td.color | 1（要素名）+ 1（要素名）+ 1（要素名）+ 10（クラス属性）| 13点     |
| h1 div + span     | 1（要素名）+ 1（要素名）+ 1（要素名）            | 3点      |
| li:last-child     | 1（要素名）+ 1（擬似クラス）                   | 2点      |


※ただし、クラスを10個以上付ければID属性の詳細度を超える訳ではないので注意してください。  
（10個以上の点数は無視されると考えてください）
