
# ブロック要素とインライン要素

displayプロパティとは、要素の「表示形式」を指定するプロパティです。  
大きく分けて「ブロック要素」と「インライン要素」があります。

すべてのHTMLタグにdisplayプロパティの初期値が決まっており、ウェブページでは、ほとんどの要素が `display: block` か `inline` のどちらかとなっています。



![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-display1.png)

<br><br><br>


## ブロック要素

`p、div、ul、h1〜h6、ul、li` などタグの初期値

横全体に広がり要素の前後に改行が入ります。  
Webサイトのレイアウトの骨組みに使う要素です。

<br><br><br>

## インライン要素
`a、span、strong、img` などのタグの初期値

ブロック要素の中身の文章などの要素。  
横に並ぶからといってレイアウトの骨組みには用いない。  
なぜなら横幅（`width`）や余白（`margin`や`padding`）が正しく設定できないからです。


インライン要素に `padding` や `margin` を設定して、どのように崩れるかを試しに確認してみましょう。

```html
<div>大きく分けて<strong>「ブロック要素」</strong>と<strong>「インライン要素」</strong>があります。</div>
```
```css
div {
  width: 500px;
  background-color: orange;
}
strong {
  padding: 20px;
  margin: 30px 30px 0 100px;
  background-color: skyblue;
}
```


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-display2.png)

<br><br><br>

## インラインブロック要素

ブロック要素とインライン要素それぞれの特徴を併せ持っている要素。  
文章中の指定した文字に対して装飾をしたい時に便利なdisplay属性です。


### 例


```html
<ol>
  <li><a href="#">HOME</a></li>
  <li><a href="#">会社概要</a></li>
  <li class="current">財務業況</li>
</ol>
```
```css
li {
  display: inline-block;
  margin-right: 10px;
}
li::after {
  content: ">";
  margin-left: 10px;
}
li:last-of-type::after {
  content: "";
  margin-left: 0;
}
a {
  color: #333;
}
.current {
  padding: 16px;
  background-color: palegreen;
}
```

<p class="codepen" data-height="300" data-theme-id="light" data-default-tab="result" data-user="cotton" data-slug-hash="XWmVgpM" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="inline-blickでパンくずを作る">
  <span>See the Pen <a href="https://codepen.io/cotton/pen/XWmVgpM">
  inline-blickでパンくずを作る</a> by cotton (<a href="https://codepen.io/cotton">@cotton</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

外側はインライン要素、内側はブロック要素。

「パンくず」や「文章中の指定した文字に装飾をしたい時」に便利なdisplay属性。

HTMLタグには初期設定されておらず、displayプロパティで指定する必要がある。

