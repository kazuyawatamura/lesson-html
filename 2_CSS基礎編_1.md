# 2. CSS基礎編1


## CSS（スタイルーシート）とは

**Cascading Style Sheetsの略**
HTMLが文章構造を指定する言語であるのに対して、
CSSはそのHTML文章のレイアウトや装飾などの見た目を指定する為の言語です。



![](https://d2mxuefqeaa7sj.cloudfront.net/s_3066FA23A18E1433BC4D48A1112B9F0C6A766C9E0917C880D3A50377E5D58EB4_1520566501261_HTML.png)



![](https://d2mxuefqeaa7sj.cloudfront.net/s_3066FA23A18E1433BC4D48A1112B9F0C6A766C9E0917C880D3A50377E5D58EB4_1520567145555_CSS.png)



---
## CSSの基本的な書き方


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1520926483939_CSS.png)



- セレクター　：　適用する対象　　　　　← どれ
- プロパティ：　スタイルの種類　　　　← 何を
- 値　　　　：　適用させたい結果　　　← どうするか

### POINT

- プロパティと値は波括弧で囲う
- プロパティと値はコロン（：）でつないでセミコロン（；）で終わる


```css
p {
　color: red;
　font-weight: bold;
　margin-left: 20px;
}
```
↓
```css
pタグの {
　色を: 赤にする;
　太さを: 太くする;
　左側の隙間を: 20pxにする;
}
```

---
## 記述する場所について


### 1.HTMLタグに直接記述する

```html
<p style="color: red;">この文字を赤にしたい。</p>
```

### 2.head要素内に記述する

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>セレクタの練習1</title>
    <style>
      p {
      　color: red;
      }
    </style>
  </head>
  <body>
  　<p>この文字を赤にしたい。</p>
  </body>
</html>
```

### 3. 外部ファイルに記述する
```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>セレクタの練習1</title>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
  　<p>この文字を赤にしたい。。</p>
  </body>
</html>
```

```css
/* style.css の中身 */
p {
　color: red;
}
```
---
## CSSのコメントの書き方

```css
/* コメントを書いて分かりやすいスタイルシートを書こう */

/*
    コメントは複数行でも記述できます。
    説明やメッセージなどを残せます。
*/
```

---
## セレクターについて

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>セレクタの練習</title>
    <style>
    　★ここにスタイルシートを書く★
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


### 代表的なセレクター一覧（selector1.html）

#### 1. 全称セレクター
```css
* {
　color: blue;
}
```

#### 2. インラインStyle属性
```html
<p style="color: red;">インラインスタイル</p>
```


#### 3. タグセレクター

```<p>``` タグの文字色を赤にしてください。
```css
p {
  color: red;
}
```

#### 4. IDセレクター

```id-selector```のIDが付いた要素の文字色を水色にしてください。

```html
<div id="id-selector">IDセレクタで文字の色を変える</div>
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


#### 5. クラスセレクター

```hello-wrapper``` クラスがついた要素の文字色をオレンジ色にしてください。

```css
.hello-wrapper {
  color: orange;
}
```


#### 6. 複数一括セレクター

```.goodbye``` クラスと```.hello```クラスが付いた要素の文字色をグレーにしてください。

```css
.goodbye, .hello {
  color: gray;
}
```

#### 7. 子孫セレクター
```css
.hello-wrapper .hello {
  color: tan;
}
```


### クラスの付け方のルールや注意点


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


### 他にもあるセレクター（selector2.html）

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

#### 8. 子セレクター

```css
/* よくない例 */
.news-area ul li {
  color: #skyblue;
}

.news-area > ul li {
  color: #skyblue;
}
```

#### 9. 隣接セレクター

```css
.news-area .news-area-main li + li {
  background-color: pink;
}
```


### まだまだあるセレクター（selector3.html）
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

#### 10. 擬似クラス

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


---
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
