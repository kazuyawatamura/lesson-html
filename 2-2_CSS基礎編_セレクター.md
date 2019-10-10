# CSS基礎編 セレクターについて

## 代表的なセレクター一覧（selector1.html）


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
![](https://paper-attachments.dropbox.com/s_99F560811FA13A2097A0AA539193AC772188AA6753D14D87F45BFD10DB837A23_1570716584327_+2019-10-10+23.09.18.png)




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



### 全称セレクター



```css
* {
　color: blue;
}
```


### 書いて覚えよう

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

```css
.news-area .news-area-main li + li {
  background-color: pink;
}
```


## まだまだあるセレクター（selector3.html）
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
</ul>
```

### 10. 擬似クラス

- hover　　　　　 → カーソルが乗っている要素


- first-child　　　 → 要素内の最初の子要素
    - ■□□□□□□□□
- last-child　　　 → 要素内の最後の子要素
    - □□□□□□□□■
- nth-child(n)　　 → 要素内のn番目の子要素
    - □□■□□□□□
- nth-child(odd)　→ 要素内の奇数の子要素
    - ■□■□■□■□
- nth-child(even)  → 要素内の偶数の子要素
    - □■□■□■□■
- nth-child(n + 5) → 5個目以降のliを指定する場合
    - □□□□■■■■
- nth-child(-n + 5) → 5個目までを指定する場合
    - ■■■■■□□□


```css
/* カーソルが乗っている要素 */
.main-menu li a:hover {
  background-color: red;
  text-decoration: none;
}

/* 最初の要素 */
.main-menu li:first-child {
  background-color:#faa;
}
/* n番目の要素 */
.main-menu li:nth-child(2), .main-menu li:nth-child(3) {
  background-color:#afa;
}
/* 最後の要素 */
.main-menu li:last-child {
  background-color: #aaf;
}
/* 奇数の要素 */
.main-menu li:nth-child(odd) {
  background-color:#faf;
}
/* 偶数の要素 */
.main-menu li:nth-child(even) {
  background-color:#ffa;
}
/* 3の倍数の要素 */
.main-menu li:nth-child(3n) {
  background-color:#aff;
}
/* 3の倍数プラス1の要素 */
.main-menu li:nth-child(3n+1) {
  background-color:#aff;
}
```

参考サイト： [nth-childジェネレーター](http://www.bad-company.jp/nth-child/)



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
