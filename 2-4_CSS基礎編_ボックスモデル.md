# CSSボックスモデルについて

ここでは横幅や縦幅を設定したり、要素間の余白を設定することのできるプロパティについてお伝えします。
前提としてサイトのレイアウトに用いるのはブロック要素（次ページで解説します）です。
`<span>` や `<a>` では書かずに `<div>` などで記述していきましょう。

## width（ウィズ）

**（box-model.html）**

要素の横幅の指定をするプロパティ。
サイトレイアウト時には必ず用いるプロパティです。




### 初期値： auto

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511306636_width1.png)

ブロック要素（後述します）何も指定しないと要素の幅は自動でブラウザ幅いっぱいに広がります。

以下のようにすると500pxの細長いブロックができると思います。

```html
<div class="width">横幅</div>
```
```css
.width {
  width: 500px; /* 初期値はauto */
  background-color: skyblue;
}
```

### 親要素の幅 > 子要素の幅にする

子要素の幅は親要素よりも小さくしてください。
はみ出してしまうとレイアウトが難しくなるので、親要素の幅以内にしておきましょう。
または、 `width: auto`（初期値のまま）で構いません。

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511286290_width2.png)


### 親要素を固定、 % での指定

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511295581_width3.png)



## height（ハイト）

高さの指定をするプロパティ。
Webサイトをレイアウトする上で、高さは可変するものだと考えがあるため `height` を設定する事はあまりありません。
ボタンなどのパーツで指定する場合があるので覚えておきましょう。

### 初期値：auto

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521185592542_height1.png)


`width: auto` と異なり、`height` は縦いっぱいには広がりません。
文字や画像などの要素の中身の分だけの高さになります。

固定値500pxを指定してみましょう。

```html
<div class="height">高さ</div>
```
```css
.height {
  height: 500px; /* auto */
  background-color: skyblue;
}
```

### 親要素のheightが指定されていないと%指定は効かない

こちらもあまり指定することはありませんが、高さを % パーセントで設定したい時は覚えておきましょう。

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521189557925_height2.png)



## padding（パディング）と　margin（マージン）

下記の図を見てください。

- padding：要素の内側の余白
- margin  ：要素の外側の余白

### ボックスモデルの概念図

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521520448558_.png)


#### Google Chrome の Developer Tool の右下にも

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522025206507_+2018-03-26+9.46.01.png)




### 基本的な書き方

**padding-margin.html**

```html
<div class="top">上部</div>
<div class="middle">マージンとパッディング</div>
<div class="bottom">下部</div>
```
```css
.top {background: skyblue;}
.middle {
  background: orange;
  margin-top: 20px;
  margin-right: 0;
  margin-bottom: 60px;
  margin-left: 40px;
  
  padding-top: 20px;
  padding-right: 40px;
  padding-bottom: 0;
  padding-left: 100px;
}
.bottom {background: silver;}
```

#### 値のショートハンド

##### その1
```css
.middle {
  background: orange;
  margin: 20px 0 60px 40px;
  padding: 20px 40px 0 100px;
}
```

順番に「上、右、下、左」

##### その2
```css
.middle {
  background: orange;
  margin: 20px 0 60px;
  padding: 20px 40px 0;
}
```

順番に「上、左右、下」

##### その3
```css
.middle {
  background: orange;
  margin: 20px 60px;
  padding: 20px 0;
}
```

順番に「上下、左右」



### マージンの相殺

マージンの指定が隣接すると、適用されるマージンは値が大きい方しか適用されないません。



![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511844583_1.png)

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511848915_2.png)


※左右のマージンは相殺されない



### 要素を左右真ん中に配置するテクニック

「px」「%」という単位ではなく、「auto」という値を指定することで、要素を左右真ん中配置にする事ができます。


```html
<div class="auto-center">
  <p class="text">要素を左右真ん中配置にする事ができます。</p>
</div>
```
```css
.auto-center {
  background-color: #EEEEEE;
}
.auto-center .text {
  width: 100px;
  margin: 0 auto;
  background-color: skyblue;
}
```


![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521514597741_3.png)


また、横幅（width: 100px）を指定した状態で、marginの左右のどちらかにautoを指定すると、指定した方に数値を自動的に算出します。

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522025972526_4.png)


#### 注意点

- `margin: auto 0;` では、上下中央配置はできない。
- `padding: 0 auto;` では、中央配置はできない。
