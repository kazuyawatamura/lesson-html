# CSS基礎編 プロパティについて

**properties1.html**

<br><br><br>

## 文字の色・大きさ・太さ

```html
<div class="text">文字の色・大きさ・太さ</div>
```
```css
.text {
  color: #40dce8; /* rgba(64, 220, 232, 100) */
  font-size: 16px; /* px, em, %, rem */
  font-weight: normal; /* normal, bold, 400, 800 */
  text-decoration: underline; /* none, underline */
}
```
<br><br><br>

### 何も指定していない時のそれぞれの初期値（デフォルト）

```css
.class {
  color: #000000;
  font-size: 16px;
  font-weight: normal;
  text-decoration: underline;
}
```

ただし　```<a>``` タグの ```text-decoration``` の初期値（デフォルト）は、```underline```（下線有り）です。

<br><br><br>

---

<br><br><br>

## カラーコードについて

CSSで色を設定する際に3通りの指定方法があります。

<br><br><br>

### 16進数のカラーコード

よく使用する指定方法です。  
耳慣れない16進数という言葉ですが、Photoshopなどのデザインツールから値をコピーしてCSSに貼り付けることが多いため、「この値は○○色」と具体的に覚えなくても大丈夫です。  
※ 無彩色の数種類は覚えても良いかもしれません。  

**無彩色カラーの一部**
`#FFFFFF` →　白
`#FAFAFA` →　限りなく薄いグレー
`#CCCCCC` →　グレー
`#000000` →　黒

6桁の値の2桁ずつがRGBのそれぞれの値です。  
RGBは「加法混合」といって、赤青緑の3種類の色を混ぜれば混ぜるほど白に近づきます。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property1.png)

* [RGBとは](https://www.designmeishi.net/meishidatabase/color/)

それぞれの値をこの16進数で表現します。  
`F` に近づくほど色が強く出て、`0` に近づくほど色は弱くなります。

赤青緑のそれぞれの色をすべて強く出したら白になり、すべての色を弱めたら黒、と覚えましょう。


**黒** ← 　0, 1, 2, 3, 4, 5, 6, 7, 8, 9, a, b, c, d, e, f　→ **白**

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property2.png)



```css
/* 文字色 */
color: #FF0000;

/*背景色*/
background-color:  #FF00FF;
```
<br><br><br>

### rgba

RGBの値を0〜255までの数字で指定する方法です。
大きな特徴は、Alpha（透明度）を指定することができる指定方法です。
背景色に指定する事によって、半透明が表現できるのでデザインの幅が広がります。

* 黒← 　`0` 〜 `255`　→白
* 透明← `0` 〜 `1` →不透明
  * `0.5` を `.5` と記述することもできます。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property3.png)

```css
/* 文字色 */
color: rgba(255, 0, 0, 1);

/*背景色*/
background-color:  rgba(0, 0, 0, 0.5);
```
<br><br><br>

### カラーネーム

Black、Navy、Aquaなど色の名前を指定する方法です。

```css
/* 文字色 */
color: paleGreen;

/*背景色*/
background-color: skyblue;
```

<br><br><br>

### `color` と　`background-color` の初期値

使用することは少ないですが、`color` と `background-color` の初期値があることを覚えておいてください。

```css
/* 文字色 */
color: transparent;

/*背景色*/
background-color: transparent;
```


* [カラーコード 早見表](http://www5.plala.or.jp/vaio0630/hp/c_code.htm)
* [カラーコード変換ツール](https://tech-unlimited.com/color.html)

---

## 単位について

### px（ピクセル）

- 絶対値
- CSSで数値を指定するさいの基本的な単位は `px` ピクセルと覚えておきましょう。

### %（パーセント）

- 相対値
- 親要素のフォントサイズの倍率

```css
.percent-wrapper {
  font-size: 75%; /* 12px */
}
.percent {
  font-size: 200%; /* 12px * 2 = 24px */
}
```

[PXtoEM.com PX to EM conversion made simple.](http://pxtoem.com/)

<br><br><br>

### rem（レム / ルートエム）

- 相対値
- emと同じような考え方だが、ルート（htmlタグ）に対する割合のサイズ

**主にフォントサイズの指定に使います。**

`％` や `em` と同様に相対値ですが、ルート（html）の値を参照するため、計算が楽でメンテナンス性にも優れています。

とくにレスポンシブサイトで効果を発揮し、スマホ時に文字を大きくしたい場合は、`font-size: 10px;` を `font-size: 20px;` にすれば、サイト全体の文字サイズが2倍になります。


```css
html {
  font-size: 10px;
}
.rem {
  font-size: 3rem; /* 10px * 3(rem) = 30px */
}
```

下記はサイト全体の文字サイズは、```14px``` 相当だが、タイトルの文字サイズ ```16px``` 相当に指定できます。

```html
<h1 class="title">ヘッダータイトル</h1>
<p class="description">吾輩は猫である。名前はまだ無い。どこで生れたかとんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれ</p>
```

```css
html {
  font-size: 10px;
}
body {
  font-size: 1.4rem;
}
.title {
  font-size: 1.6rem;
}
```

<br><br><br>
---
<br><br><br>

## 文字を左右中央に寄せる

ブロック要素内（もしくはインラインブロック要素内）で中央寄せにできます。
インライン要素でこの指定をしても横幅が内容分の横幅なので中央寄せは効きません。


```html
<div class="text-align">文字を左右中央に寄せる</div>
```
```css
.text-align {
  text-align: center; /* 初期値は left */
}
```

<br><br><br>
---
<br><br><br>

## 行間を指定する

```html
<div class="line-height">行間を指定する。行間を生むために長文を打ってください。サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト。</div>
```

```css
.line-height {
  line-height: 2;
}
```


- 文字サイズの倍率を指定
- 単位は付けずに記述することが一般的


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property4.png)

<br><br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property5.png)

<br><br><br>
---
<br><br><br>

## 背景色の指定

```html
<div class="background-color">背景色の指定</div>
```

CSSでも指定の仕方は3通りあります

```css
.background-color {
  background-color: #FF0000;
}
```

```css
.background-color {
  background-color: rgba(255, 0, 0, 1);
}
```

```css
.background-color {
  background-color: red;
}
```

<br><br><br>
---
<br><br><br>

## 線を引く

要素の上下左右にそれぞれ線を引くことができます。
指定できるプロパティは下記の通りです。

* 太さ
* スタイル
* 色

```html
<p class="border">この周りに線を描きます</p>
```
```css
.border {
  border-width: 1px;
  border-style: solid;
  border-color: palegreen;
}
```

<br><br><br>

### ショートハンド

```css
.border {
  border: 1px solid palegreen;
}
```
<br><br><br>

### 線スタイルの種類

- solid（実線）
- dotted（点線）
- dashed（破線）
- double（2重線）

```html
<p class="solid">2px solid grayの場合</p>
<p class="dotted">2px dotted grayの場合</p>
<p class="dashed">2px dashe grayの場合</p>
<p class="double">2px double grayの場合</p>
```
```css
.solid { border: 2px solid gray;}
.dotted { border: 2px dotted gray;}
.dashed { border: 2px dashed gray;}
.double { border: 5px double gray;}
```
<br><br><br>

### 上下左右、個別に線をひく

- 上にだけ線を引く：**border-top**:〜
- 下にだけ線を引く：**border-bottom**:〜
- 左にだけ線を引く：**border-left**:〜
- 右にだけ線を引く：**border-right**:〜

```html
<p class="solid-bottom">2px solid grayの場合</p>
```
```css
.solid-bottom {
  border-bottom-width: 2px;
  border-bottom-style: solid;
  border-bottom-color: gray;
}
```
<br><br><br>

### ショートハンド
```css
.solid-bottom { border-bottom: 2px solid gray;}
```

<br><br><br>
---
<br><br><br>

## 背景画像

**properties2.html**

```html
<div class="background">背景画像の指定</div>
```
```css
.background {
  width: 100px;
  height: 30px;
  background-image: url(../assets/images/logo.png);
  background-repeat: no-repeat;
  background-position: 0 0;
}
```
<br><br><br>

### background-image
背景画像を指定するプロパティ

<br><br><br>

### background-repeat
背景画像のリピートの仕方を指定するプロパティ

```css
background-repeat: no-repeat;
background-repeat: repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;
```
<br><br><br>

### background-position

背景画像の表示開始位置を指定するプロパティ
水平位置と垂直位置の順で半角スペースを用いて区切って指定します。

```css
background-position: top left;
background-position: center center;
```

```css
垂直方向：
top    /* 上端 */
center /* 中央 */
bottom /* 下端 */

水平方向：
left   /* 左端 */
center /* 中央 */
right  /* 右端 */
```
数値を入れる事も可能。その場合は、基準位置は左上になる。

```css
background-position: 50% 50%; /* -> center center 同義 */
background-position: 10px 40px;
```
```css
background-position: bottom 10px right 30%;
```

<br><br><br>

### ショートハンド

```css
background: #FFFFFF url(../assets/images/logo.png) no-repeat 10px 40px;
```
<br><br><br>

### おまけ：background-size

背景画像のサイズを指定するプロパティ

```css
background-size: auto; /* 初期値 */
background-size: contain; /* 縦横比を保ち、画像を最大まで大きくする */
background-size: cover; /*縦横比を保ち、表示エリアに余白がでないように画像が拡大・縮小し、切り取られる*/
background-size: 50px 50px;
background-size: 100% 40%;
```

[background-size リファレンス](http://www.htmq.com/css3/background-size.shtml)
[background-sizeプロパティについてまとめ](https://www.tam-tam.co.jp/tipsnote/html_css/post6015.html)

<br><br><br>

---

<br><br><br>

## フォントを指定する

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property6-scaled.png)


Webサイトに表示される文字（フォント）の指定を、font-familyというプロパティで設定します。
フォントには角ばっていて硬い印象のフォントや、丸みを帯びたフォントなどさまざまなフォントがあります。

```html
<h1 class="font-family">Font Hello、フォントを指定する</h1>
```
```css
.font-family {
  font-family: "Avenir Next" , Gadugi , "ヒラギノ丸ゴ ProN" , メイリオ , sans-serif;
}
```



![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property7.png)


<br><br><br>


### 基本的に複数のフォントを指定する

OS毎（Mac / Windows / iOS）にインストールされているフォンが違うため、基本的には複数指定します。
（Macにしか入っていないフォントを指定してもWindowsパソコンで表示されない等…）


<br><br><br>

### 左に指定されているフォントから優先される

下記だと  ```Avenir Next```  が無かったら、 ```Gadugi```  →  ```ヒラギノ丸ゴ```  →  ```メイリオ```  の順

<br><br><br>

### 英語フォントを先に記述する

- 英語フォントは、英語だけ
- 日本語フォントは、英語と日本語

英語フォントを先に書くことにによって、英語は英語フォントで表示できるようになります。
（英語は英語フォントの方がキレイで整っている場合が多い）


> Macのスクリーンショット（Futuraとヒラギノ丸ゴ ProNが適用されている）


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property8.png)

> Windowsのスクリーンショット（Gadugiとメイリオが適用されている）


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-property9.png)

<br><br><br>

### 総称フォントとは？

指定したフォントがまったく入っていなかったら「せめてこういう系統のフォントを表示したい」という指定になります。
ざっくりとした指定なので、実際にどんなフォントが使われるかはブラウザしだになります。

<br><br><br>

### sans-serif　or　serif

この講座内では、

```css
font-family: sans-serif;
```
でも構いません。

**Font-familyを生成してくれる便利なWebサービス（若干情報が古いです）**
[Font-familyメーカー](https://saruwakakun.com/font-family)

<br><br><br>
----------
<br><br><br>

もっとたくさんのスタイルシートみる
[スタイルシートリファレンス（目的別）](http://www.htmq.com/style/)

