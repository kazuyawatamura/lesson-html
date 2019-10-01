# 2. CSS基礎編 3（ボックスモデル、display）

# 
# 
# ボックスモデル（box-model.html）


## width（ウィズ）

横幅の指定をするプロパティ


    <div class="width">横幅</div>


    .width {
      width: 500px; /* auto */
      background-color: skyblue;
    }

初期値：auto

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511306636_width1.png)

> ブロック要素（後述します）何も指定しないと要素の幅は自動で決められる。

**親要素の幅 > 子要素の幅にする**

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511286290_width2.png)


**親要素を固定、 % での指定**

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511295581_width3.png)



## height（ハイト）

高さの指定をするプロパティ


    <div class="height">高さ</div>


    .height {
      width: 500px; /* auto */
      background-color: skyblue;
    }

初期値：auto

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521185592542_height1.png)


width: auto と異なり、heightは縦いっぱいには広がりません。
文字や画像などの要素の中身の分だけの高さになります。

**親要素のheightが指定されていないと%指定は効かない**

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521189557925_height2.png)





## padding（パディング） と　margin（マージン）（padding-margin.html）


- padding：要素の内側の余白
- margin  ：要素の外側の余白

**ボックスモデルの概念図**

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521520448558_.png)


**Google Chrome の Developer Tool にも**

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522025206507_+2018-03-26+9.46.01.png)




**基本的な書き方**


    <div class="top">上部</div>
    <div class="middle">マージンとパッディング</div>
    <div class="bottom">下部</div>


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


**値のショートハンド**

その1

    .middle {
      background: orange;
      margin: 20px 0 60px 40px;
      padding: 20px 40px 0 100px;
    }


> 順番に「　上　、　右　、　下　、　左　」

その2

    .middle {
      background: orange;
      margin: 20px 0 60px;
      padding: 20px 40px 0;
    }


> 順番に「　上　、　左右　、　下　」

その3

    .middle {
      background: orange;
      margin: 20px 60px;
      padding: 20px 0;
    }


> 順番に「　上下　、　左右　」



## マージンの相殺

マージンの指定が隣接すると、適用されるマージンは値が大きい方しか適用されないません。



![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511844583_1.png)

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521511848915_2.png)


※左右のマージンは相殺されない


## 
## 
## 
## 要素を左右真ん中に配置するテクニック

「px」「%」という単位ではなく、「auto」という値を指定することで、要素を左右真ん中配置にする事ができます。



    <div class="auto-center">
      <p class="text">要素を左右真ん中配置にする事ができます。</p>
    </div>


    .auto-center {
      background-color: #EEEEEE;
    }
    .auto-center .text {
      width: 100px;
      margin: 0 auto;
      background-color: skyblue;
    }
![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521514597741_3.png)


また、横幅（width: 100px）を指定した状態で、marginの左右のどちらかにautoを指定すると、指定した方に数値を自動的に算出します。

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522025972526_4.png)


**注意点**

- `margin: auto 0;` では、上下中央配置はできない。
- `padding: 0 auto;` では、中央配置はできない。
## 
## box-sizing プロパティ


> 要素の幅（width）や高さ（height）の中にpaddingとborderを含めるかどうか


    /* paddingとborderを幅と高さに含めない */
    box-sizing: content-box; /* 初期値 */
    
    /* paddingとborderを幅と高さに含める */
    box-sizing: border-box;



    <p class="box-sizing">要素の幅や高さに含めるかどうか。</p>


    .box-sizing {
      box-sizing: border-box;
      width: 300px;
      padding: 20px;
      border: 1px solid orange;
    }


**content-box の場合**


> paddingとborderを幅(width)と高さ(height)に含めない（幅(width)と高さ(height)に足される）


![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521520578504_2.png)




**border-box の場合**


> paddingとborderを幅(width)と高さ(height)に含める


![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521522172887_3.png)


content-boxの場合、width + padding + border を足した幅を計算しなければならず使いづらいので
理由がない限り、border-boxを指定します。

下記をオマジナイのように書くと、pタグやクラスに1つひとつ要素に指定せず、記述するHTMLすべての要素が  `border-box`  になります。


    html {
      box-sizing: border-box;
    }
    *, *::before, *::after {
      box-sizing: inherit;
    }



**※width:100%とautoの違いは？**

![](https://paper-attachments.dropbox.com/s_BC4F8A59D54929D0D4950267E6E46E1369E40AC5CCA7E973F87B06577856D766_1523524467522_4.png)

- auto：widthの中にpaddingとborderが含まれる。
- 100%：widthにはpaddingとborderの分が含まれません。

上記の   `box-sizing: border-box;` をすれば特に意識する必要はありません。
※marginは除く




----------


# display プロパティ

displayプロパティとは、要素の「表示形式」を指定するプロパティです。
大きく分けて「ブロック要素」と「インライン要素」があります。

全てのHTMLタグにdisplayプロパティの初期値が決まっており、
ウェブページでは、ほとんどの要素がdisplay: blockかinlineのどちらかとなっています。


## ブロック要素


> p、div、ul、h1〜h6、ul、li などタグの初期値

Webサイトのレイアウトの骨組みに使う要素。



## インライン要素
> a、span、strong、imgなどのタグの初期値

ブロック要素の中身の文章などの要素。
横に並ぶからといってレイアウトの骨組みには用いない。



## インラインブロック要素
> ブロック要素とインライン要素それぞれの特徴を併せ持っている要素

文章中の指定した文字に装飾をしたい時」に便利なdisplay属性。


![](https://paper-attachments.dropbox.com/s_BC4F8A59D54929D0D4950267E6E46E1369E40AC5CCA7E973F87B06577856D766_1560259053088_display1.png)





    <div>大きく分けて<strong>「ブロック要素」</strong>と<strong>「インライン要素」</strong>があります。</div>


    div {
      width: 500px;
      background-color: orange;
    }
    strong {
      padding: 20px;
      margin: 30px 30px 0 100px;
      background-color: skyblue;
    }


![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521546552358_image.png)



    <ul>
      <li>ホーム</li>
      <li>会社概要</li>
      <li>お問い合わせ</li>
    </ul>


    ul {
      text-align: center;
      padding: 20px;
      border: 1px solid #EEE;
      background: #FAFAFA;
    }
    li {
      display: inline;
      background: orange;
    }



----------


# 練習1


-  `box-sizing: border-box`  に
- 全体の横幅：300px
- 中央配置
- 線の色：#CCCCCC
- 先の太さ：3px
- 文字のサイズ：16px
- 文字と線の余白：26px


## menu1_自分の名前.html


![](https://paper-attachments.dropbox.com/s_D94100F0E1C8FCA63375B32FC348D74C30BACD40D1A9BF0C8113BA40D62FA891_1562406615612_+2019-07-06+18.50.08.png)



# 練習2
- 全体の横幅：300px
- 中央配置
- 文字の色：#000000
- 線の色：#CCCCCC
- リンクのアンダーライン無し
- 先の太さ：3px
- 文字のサイズ：16px
- 文字と線の余白：26px
- 偶数行の背景色：#EEEEEE
- マウスオン時の背景色：#C0F1FF

文字以外の白い部分もクリッカブルエリア（リンク）になるようにコーディングしてください。




## menu2_自分の名前.html
![](https://paper-attachments.dropbox.com/s_D94100F0E1C8FCA63375B32FC348D74C30BACD40D1A9BF0C8113BA40D62FA891_1562406828829_+2019-07-06+18.53.36.png)




----------
# inline-block（inline-block.html）

「パンくず」や「文章中の指定した文字に装飾をしたい時」に便利なdisplay属性。

HTMLタグには初期設定されておらず、displayプロパティで指定する必要がある。


![](https://paper-attachments.dropbox.com/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522142565672_display1.png)





    <ol>
      <li><a href="#">HOME</a></li>
      <li><a href="#">会社概要</a></li>
      <li class="current">財務業況</li>
    </ol>


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


**実習**

![](https://paper-attachments.dropbox.com/s_A61401A7231D38E995B48BE32669F918E21E6DC752D2B9DB377F898A03BF40E8_1536023294019_+2018-09-04+10.08.00.png)

![](https://paper-attachments.dropbox.com/s_A61401A7231D38E995B48BE32669F918E21E6DC752D2B9DB377F898A03BF40E8_1536023567999_+2018-09-04+10.08.00.png)




----------
# Reset.css


- [Eric Meyer’s “Reset CSS” 2.0](https://meyerweb.com/eric/tools/css/reset/)
    - 最も使われているリセットCSS
- [html-5-reset-stylesheet](http://html5doctor.com/html-5-reset-stylesheet/)
    - Eric Meyer’s CSS reset を HTML5 で使うために修正したもの
- [Normalize css](https://necolas.github.io/normalize.css/)
    - デフォルトのスタイルはあえて残しつつ、ブラウザごとの違いを修正するという考え方で作られている。
- [ress](https://coliss.com/articles/build-websites/operation/css/modern-css-reset-ress.html)
    - 上記のNormalize.css をカスタマイズしたリセットCSS
- 自作


