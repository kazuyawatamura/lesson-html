# 2-3_CSS基礎編_プロパティ（properties1html）

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

それぞれの初期値（デフォルト）は、#000000、16px、normal、none


## カラーコードについて

[カラーコード 早見表](http://www5.plala.or.jp/vaio0630/hp/c_code.htm)

### 16進数のカラーコード

黒← 　0, 1, 2, 3, 4, 5, 6, 7, 8, 9, a, b, c, d, e, f　→白


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521170368133_.png)


### rgba

黒← 　0 〜 255　→白
透明← 0 〜 1 →不透明

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1562395570706_rgba.png)




## 単位について（font-size.html）

### px（ピクセル）

- 絶対値
- ユーザーがブラウザからそのサイズを変更する事ができない

### em（エム）

- 相対値
- 親要素のフォントサイズの倍率

```html
<div class="px">pxを使ったフォントサイズ</div>
<div class="em">emを使ったフォントサイズ</div>
<div class="percent-wrapper"><p class="percent">パーセントを使ったフォントサイズ</p></div>
<div class="rem">remを使ったフォントサイズ</div>
```
```css
.px {
  font-size: 16px;
}
.em {
  font-size: 0.5em;
}
```

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


### rem（レム / ルートエム）

- 相対値
- emと同じような考え方だが、ルート（htmlタグ）に対する割合のサイズ

```css
html {
  font-size: 100%; /* 16px */
}
.rem {
  font-size: 3rem; /* 16px * 3(rem) = 48px */
}
```

```％```や```em```と同様に相対値ですが、ルート（html）の値を参照するため、計算が楽でメンテナンス性にも優れている。

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

## 文字を左右中央に寄せる

```html
<div class="text-align">文字を左右中央に寄せる</div>
```
```css
.text-align {
  text-align: center; /* 初期値は left */
}
```


## 行間を指定する

```html
<div class="line-height">行間を指定する</div>
```

```css
.line-height {
  line-height: 2;
}
```


- 文字サイズの倍率を指定
- 単位は付けずに記述することが一般的


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522845201939_.png)




![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521177549564_2.png)


## 背景色の指定
**properties2.html**

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


## 線を引く

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

### ショートハンド

```css
.border {
  border: 1px solid palegreen;
}
```

### 線の種類

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

### ショートハンド
```css
.solid-bottom { border-bottom: 2px solid gray;}
```



## 背景画像（background-image.html）

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

### background-image
背景画像を指定するプロパティ

### background-repeat
背景画像のリピートの仕方を指定するプロパティ

```css
background-repeat: no-repeat;
background-repeat: repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;
```

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
### ショートハンド

```css
background: #FFFFFF url(../assets/images/logo.png) no-repeat 10px 40px;
```

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




## フォントを指定する

![](https://paper-attachments.dropbox.com/s_2582435CB886887D060D48AAD474CC3D5EFC64DCE8C72CEB83A15ED7D7AAEB60_1570003509949_+2019-10-02+17.04.11.png)


Webサイトに表示される文字（フォント）の指定を、font-familyというプロパティで設定します。
フォントには角ばっていて硬い印象のフォントや、丸みを帯びたフォントなどさまざまなフォントがあります。

```html
<h1 class="font-family">Font Hello、フォントを指定する</h1>
```
```css
.font-family {
  font-family: 'Avenir Next' , Gadugi , 'ヒラギノ丸ゴ ProN' , メイリオ , sans-serif;
}
```



![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522220757855_font-family.png)




### 基本的に複数のフォントを指定する

OS毎（Mac / Windows / iOS）にインストールされているフォンが違うため、基本的には複数指定します。
（Macにしか入っていないフォントを指定してもWindowsパソコンで表示されない等…）


### 左に指定されているフォントから優先される

下記だと  `Avenir Next`  が無かったら、 `Gadugi`  →  `ヒラギノ丸ゴ`  →  `メイリオ`  の順


### 英語フォントを先に記述する

- 英語フォントは、英語だけ
- 日本語フォントは、英語と日本語

英語フォントを先に書くことにによって、英語は英語フォントで表示できるようになります。
（英語は英語フォントの方がキレイで整っている場合が多い）



> Macのスクリーンショット（Futuraとヒラギノ丸ゴ ProNが適用されている）


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522221676689_+2018-03-28+16.16.47.png)

> Windowsのスクリーンショット（Gadugiとメイリオが適用されている）


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522221708091_+2018-03-28+16.20.29.png)


### 総称フォントとは？

指定したフォントがまったく入っていなかったら「せめてこういう系統のフォントを表示したい」という指定になります。
ざっくりとした指定なので、実際にどんなフォントが使われるかはブラウザしだになります。

### sans-serif　or　serif

この講座内では、

```css
font-family: sans-serif;
```
でも構いません。



----------


もっとたくさんのスタイルシートみる
[スタイルシートリファレンス（目的別）](http://www.htmq.com/style/)

