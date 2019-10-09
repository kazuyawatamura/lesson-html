
# displayプロパティ

displayプロパティとは、要素の「表示形式」を指定するプロパティです。
大きく分けて「ブロック要素」と「インライン要素」があります。

すべてのHTMLタグにdisplayプロパティの初期値が決まっており、ウェブページでは、ほとんどの要素がdisplay: blockかinlineのどちらかとなっています。



![](https://paper-attachments.dropbox.com/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522142565672_display1.png)




## ブロック要素


`p、div、ul、h1〜h6、ul、li` などタグの初期値

Webサイトのレイアウトの骨組みに使う要素。



## インライン要素
`a、span、strong、img` などのタグの初期値

ブロック要素の中身の文章などの要素。
横に並ぶからといってレイアウトの骨組みには用いない。



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


![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521546552358_image.png)


## インラインブロック要素
ブロック要素とインライン要素それぞれの特徴を併せ持っている要素

文章中の指定した文字に装飾をしたい時」に便利なdisplay属性。


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
li:after {
  content: ">";
  margin-left: 10px;
}
li:last-child:after {
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

外側はインライン要素、内側はブロック要素。

「パンくず」や「文章中の指定した文字に装飾をしたい時」に便利なdisplay属性。

HTMLタグには初期設定されておらず、displayプロパティで指定する必要がある。

