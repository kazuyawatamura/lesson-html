# 2. CSS基礎編 2


## ファイルを作成

**properties2.html**





## 背景色の指定


    <div class="background-color">背景色の指定</div>


    .background-color {
      background-color: #FF0000;
    }


    .background-color {
      background-color: rgba(255, 0, 0, 1);
    }


    .background-color {
      background-color: red;
    }




## 線で引く


    <p class="border">この周りに線を描きます</p>


    .border {
      border-width: 1px;
      border-style: solid;
      border-color: palegreen;
    }

**ショートハンド**


    .border {
      border: 1px solid palegreen;
    }

**線の種類**

- solid（実線）
- dotted（点線）
- dashed（破線）
- double（2重線）


    <p class="solid">2px solid grayの場合</p>
    <p class="dotted">2px dotted grayの場合</p>
    <p class="dashed">2px dashe grayの場合</p>
    <p class="double">2px double grayの場合</p>


    .solid { border: 2px solid gray;}
    .dotted { border: 2px dotted gray;}
    .dashed { border: 2px dashed gray;}
    .double { border: 5px double gray;}


**上下左右 個別に線をひく**


- 上にだけ線を引く：**border-top**:〜
- 下にだけ線を引く：**border-bottom**:〜
- 左にだけ線を引く：**border-left**:〜
- 右にだけ線を引く：**border-right**:〜


    <p class="solid-bottom">2px solid grayの場合</p>


    .solid-bottom {
      border-bottom-width: 2px;
      border-bottom-style: solid;
      border-bottom-color: gray;
    }


    .solid-bottom { border-bottom: 2px solid gray;}




----------
## 背景画像（background-image.html）


    <div class="background">背景画像の指定</div>


    .background {
      width: 100px;
      height: 30px;
      background-image: url(../assets/images/logo.png);
      background-repeat: no-repeat;
      background-position: 0 0;
    }

**background-image**
背景画像を指定するプロパティ

**background-repeat**
背景画像のリピートの仕方を指定するプロパティ


    background-repeat: no-repeat;
    background-repeat: repeat;
    background-repeat: repeat-x;
    background-repeat: repeat-y;

**background-position**
背景画像の表示開始位置を指定するプロパティ
水平位置と垂直位置の順で半角スペースで区切って指定します。


    background-position: top left;
    background-position: center center;
    
    垂直方向：
    top    /* 上端 */
    center /* 中央 */
    bottom /* 下端 */
    
    水平方向：
    left   /* 左端 */
    center /* 中央 */
    right  /* 右端 */

数値を入れる事も可能。その場合は、基準位置は左上になる。


    background-position: 50% 50%; /* -> center center 同義 */
    background-position: 10px 40px;


    background-position: bottom 10px right 30%;

**ショートハンド**

    background: #FFFFFF url(../assets/images/logo.png) no-repeat 10px 40px;


**おまけ：background-size**

背景画像のサイズを指定するプロパティ


    background-size: auto; /* 初期値 */
    background-size: contain; /* 縦横比を保ち、画像を最大まで大きくする */
    background-size: cover; /*縦横比を保ち、表示エリアに余白がでないように画像が拡大・縮小し、切り取られる*/
    background-size: 50px 50px;
    background-size: 100% 40%;

[background-size リファレンス](http://www.htmq.com/css3/background-size.shtml)
[background-sizeプロパティについてまとめ](https://www.tam-tam.co.jp/tipsnote/html_css/post6015.html)



----------


## フォントを指定する

文字（フォント）の指定を、font-familyというプロパティで設定します。


    <h1 class="font-family">Font Hello、フォントを指定する</h1>


    .font-family {
      font-family: 'Avenir Next' , Gadugi , 'ヒラギノ丸ゴ ProN' , メイリオ , sans-serif;
    }




![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522220757855_font-family.png)




**基本的に複数のフォントを指定する**

OS毎（Mac / Windows / iOS）にインストールされているフォンが違うため、基本的には複数指定します。
（Macにしか入っていないフォントを指定してもWindowsパソコンで表示されない等…）


**左に指定されているフォントから優先される**

下記だと  `Avenir Next`  が無かったら、 `Gadugi`  →  `ヒラギノ丸ゴ`  →  `メイリオ`  の順


**英語フォントを先に記述する**


- 英語フォントは、英語だけ
- 日本語フォントは、英語と日本語

英語フォントを先に書くことにによって、英語は英語フォントで表示できるようになります。
（英語は英語フォントの方がキレイで整っている場合が多い）



> **Macのスクリーンショット（Futuraとヒラギノ丸ゴ ProNが適用されている）**


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522221676689_+2018-03-28+16.16.47.png)

> **Windowsのスクリーンショット（Gadugiとメイリオが適用されている）**


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522221708091_+2018-03-28+16.20.29.png)


**総称フォントとは？**

指定したフォントが全く入っていなかったら「せめてこういう系統のフォントを表示したい」という指定になります。
ざっくりとした指定なので、実際にどんなフォントが使われるかはブラウザ次第になります。

**sans-serif**　or　**serif**


MacとWindowsとiOSにAndroid、しかもブラウザ毎にチラつきがあったり綺麗に表示できない問題があるので、この講座内では、


    font-family: sans-serif;

でも構いません。



----------


もっとたくさんのCSSを参考にする
http://www.htmq.com/style/

