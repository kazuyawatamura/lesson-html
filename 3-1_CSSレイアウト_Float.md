# 3. 3-1_CSSレイアウト_Float


## float（float-basic.html）

昔から使われている横並び用のCSS。
レイアウト調整用のCSSと言えばfloatだったが、本来の用途は、特定の要素を左右に寄せて配置するプロパティ。
たとえば、文章中の画像に回り込ませる為のCSSでした。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522033854828_image.png)


```html
<p class="float-text">
  クスールはWebの技術を中心に “ものづくり”を教える小さな学校です。
  <img src="https://picsum.photos/140/70" alt="" class="float-image">
  Web制作会社が運営しているので、講師は全員現役のクリエイター。オンラインでは伝えることができない、考える力と制作現場で必要なノウハウを、個人／企業に提供しています。Flash/ActionScript、HTML/CSS/JavaScriptなどのWebの技術を中心としたカリキュラムです。受講者自ら手を動かし、作品制作に必要な技術を身につけることを目的としています。また、イベントの開催、書籍の執筆を行うことで、クリエイターの交流の場や、学ぶ機会を提供しています。
</p>
```
```css
.float-text {
  width: 400px;
}
.float-image {
  float: right;
  padding: 16px;
  margin: 8px;
  background-color: #eee;
}
```

回り込みしたい要素（上記は `<img>` タグ）に対して

- float: left;と指定すれば、画像は左側に寄り、
- float: right;と指定すれば、画像は右側に寄る。
- 初期値は、 `none` 



## floatで横並び1（float-clear.html）

```html
<div class="orange">オレンジ</div>
<div class="skyblue">ブルー</div>
<div class="red">レッド</div>
```
```css
.orange {
  background-color: orange;
  width: 200px;
  height: 250px;
  float: left;
}
.skyblue {
  background-color: skyblue;
  width: 150px;
  height: 100px;
  float: left;
}
.red {
  background-color: red;
  width: 500px;
  height: 80px;
  float: left;
}
```

![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522035741946_image.png)


### 注意点

`.red`  要素から  `float: left;`  を削除してみると。。。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522036377319_image.png)



-  `.red`  要素は  `float: left`  を削除したにもかからわらず、横並びのまま
- 横幅が短くなっている

floatプロパティを適応した要素は、「浮いてしまう」ような状態になってしまいます。




![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522892722724_1.png)




### 解決策

```css
.red {
  background-color: red;
  width: 500px;
  height: 80px;
  clear: left; /* <- または、right , both */
}
```



## floatで横並び2（float-overflow.html）

```html
<div class="wrap">
  <div class="orange">オレンジ</div>
  <div class="skyblue">ブルー</div>
  <div class="red">レッド</div>
</div>
```
```css
.wrap {
  background-color: palegreen;
}
.orange {
  background-color: orange;
  width: 200px;
  height: 250px;
  float: left;
}
.skyblue {
  background-color: skyblue;
  width: 150px;
  height: 100px;
  float: left;
}
.red {
  background-color: red;
  width: 500px;
  height: 80px;
  float: left;
}
```


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522042437450_2.png)



### 解決策1（推奨）
```css
.wrap {
  overflow: hidden; /* <- 追加 */
  background-color: palegreen;
}
```

### 解決策2
縦サイズが決まっていればこの方法のほうが手っ取り早いと思いますが、レスポンシブサイトを作るのであれば面倒な手法かもしれません。

```css
.wrap {
  height 300px;　/* <- 高さを指定する */
  background-color: palegreen;
}
```

### 解決策3

htmlの方に `clearfix` というクラスを追加します。

```html
<div class="wrap clearfix">
```

そのクラスに以下のようなプロパティを設定します。

```css
.clearfix::after{
  content: "";
  display: block;
  clear: both;
}
```

クリアーフィックスという手法の解決方法です。
IEが古い時代に回避方法としてベターだったこの方法ですが、時代と共に使われなくなってきました。
古いサイトのリニューアル案件などでもしかしたら利用されているかもしれません。