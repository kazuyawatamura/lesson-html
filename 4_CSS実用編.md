# 4. CSS実用編




# 最小と最大横幅（min-max.html）

**min-width**


    <div class="min-width">
      <p class="nomin">最小幅なし</p>
      <p class="min">最小幅100px</p>
    </div>


    .min-width {
      width: 200px;/*親要素大きめ*/
      background:skyblue
    }
    .min-width .nomin {/*最小幅なし*/
      background:gray;
      width: 50%
    }
    .min-width .min {/*最小幅あり*/
      background:orange;
      width: 50%;
      min-width: 100px
    }


**max-width**


    <div class="max-width">
      <p class="nomin">最大幅なし</p>
      <p class="min">最大幅100px</p>
    </div>


    .max-width {
      width: 100px;/*親要素小さめ*/
      background:skyblue
    }
    .max-width .nomin {/*最大幅なし*/
      background:gray;
      width: 80%
    }
    .max-width .min {/*最大幅あり*/
      background:orange;
      width: 80%;
      max-width: 100px
    }







# 疑似要素（before-after.html）




![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522207364851_HTML.png)


HTMLには書かれていない要素もどきをCSSで作ることが可能になります。

疑似要素をマスターするとより幅広い表現が可能になります。
例えば、、、


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522207977692_beforeafter1.png)




    <div class="before">こんにちは</div>
    <div class="after">さようなら</div>


    .before::before {
      content: "[hello]";
      margin-right: 10px;
    }
    .after::after {
      content: "[Goodbye]";
      margin-left: 10px;
    }


- ::before ： 要素の直前に内容（content）を追加
- ::after　： 要素の直後に内容（content）を追加



## 具体的な活用方法

**テキストをかぎかっこで囲む**


    <div class="example1">これはサンプルテキストです。</div>


    .example1::before{
      content: '『';
      color: orange;
    }
    
    .example1::after{
      content: '』';
      color: orange;
    }



**タイトル文の英字を入れる**


    <h1 class="example2">タイトル</h1>


    .example2 {
      text-align: center;
    }
    
    .example2::before{
      content: 'Title';
      color: palegreen;
      font-size: 20px;
      display: block;
    }

疑似要素は初期値ではインライン要素のため、 `display: block;`  を入れて前後に改行が入るようにします。

【Extra】**data属性を使ってタイトルを入れてみる**


    <h1 data-title="title" class="example3">タイトル</h1>


    .example3 {
      text-align: center;
    }
    .example3::before{
      content: attr(data-title);
      color: palegreen;
      font-size: 20px;
      display: block;
    }



**絶対配置（position: absolute;）で、疑似要素を好きな位置に配置する**

かなり便利で表現方法が増えるので是非覚えましょう。


    <h1 class="absolute">ここにタイトルを書きます</h1>


    .absolute {
      position: relative;
    }
    .absolute::before {
      content: "";
      position: absolute;
      top: -32px;
      left: -32px;
      background: url(./assets/images/image/ico-new.png);
      width: 42px;
      height: 42px;
    }


![ico-new.png](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1522893931247_ico-new.png)



## 練習
https://www.dropbox.com/s/ii3ft2n116vyc5p/icon.zip?dl=0



![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522224752565_beforeafter2.png)




    <ul class="menu-before">
      <li class="home"><a href="#">ホーム</a></li>
      <li class="boss"><a href="#">社長メッセージ</a></li>
      <li class="company"><a href="#">会社概要</a></li>
      <li class="recruit"><a href="#">新卒採用</a></li>
      <li class="other"><a href="#">その他</a></li>
    </ul>


**ヒント**


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522232694697_beforeafter3.png)




----------
# 角丸、シャドウ、グラデーション



## 角丸（border-radius.html）

CSSで要素に対して四方に角丸を設定できるプロパティです。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522306298448_border-radius1.png)


四隅に同じ値の角丸を設定したい場合、以下のように記述します。
半径20pxの正円の円弧をベースにした角丸を実装ができます。



    <div class="radius">角丸</div>


    .radius {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      border-radius: 20px;
    }


四隅に異なる値を設定したい場合は以下のように記述します。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522306688289_border-radius2.png)




    .radius {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      border-top-left-radius: 10px;
      border-top-right-radius: 20px;
      border-bottom-right-radius: 30px;
      border-bottom-left-radius: 40px;
    }

**ショートハンド**

左上、右上、左下、右下の順に記述（左上を基準に時計回り）


    border-radius: 10px 20px 30px 40px;



## シャドウ（box-shadow.html）


要素に対して影をつけることが出来ます。



    <div class="shadow1">シャドウ</div>



**ぼかしのない影を作る**


    .shadow1 {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      box-shadow: 10px 10px;
    }


- ひとつ目の 10px が左右の値
- ふたつ目の 10px が上下の値
![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874095278_box-shadow1.png)


**左に10px、上に20px伸びる影の例**


    .shadow2 {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      box-shadow: -20px -10px;
    }



![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874108051_box-shadow2.png)


**影の色を変えつつぼかす**


    .shadow3 {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      box-shadow: 10px 10px 20px gray;
    }


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874124573_box-shadow3.png)


**影を拡大し、色も指定する**


    .shadow4 {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      box-shadow: 10px 10px 20px 10px rgba(100, 0, 0, .3);
    }


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874144913_box-shadow4.png)


**内側にシャドウを付ける**


    .shadow5 {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      box-shadow: 10px 10px 20px 0 rgba(0, 0, 0, .5) inset;
    }


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874154202_box-shadow5.png)



**カンマ区切りで内側と外側両方に影をかける**


    .shadow6 {
      width: 200px;
      height: 100px;
      background-color: skyblue;
      box-shadow: 0px 10px 16px 0px rgba(0, 0, 0, .3), 0px 5px 10px rgba(255,255,255,0.75) inset;
    }


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874163755_box-shadow6.png)

![角丸にするとボタンっぽくなりますね](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874169864_box-shadow7.png)



参考：[Box Shadowのエフェクトサンプル ＆ 便利な素材まとめ](https://www.nxworld.net/tips/box-shadow-effect.html)





## グラデーション（gradient.html）

CSSでグラデーションを設定ができます。
デザインのアクセントや要所で使うことがあるので、ぜひ覚えておきましょう。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522310087899_gradient1.png)



    <div class="gradient">グラデーション</div>


    .gradient1 {
      text-align: center;
      width: 200px;
      height: 100px;
      line-height: 100px;      
      background: linear-gradient(#FAD961, #F76B1C);
    }




**グラデーションの方向を設定する**


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522310655503_gradient2.png)



    .gradient1 {
      text-align: center;
      width: 200px;
      height: 100px;
      line-height: 100px;      
      background: linear-gradient(90deg, #FAD961, #F76B1C);
    }


> deg = degree（デグリー）

**90deg** ではなく、 `to bottom`   `to left`    `to bottom right`  でも設定ができます。



CSS Gradient Generator
https://cssgradient.io/

Gradient Gallery
https://webgradients.com/






----------
# Google Fonts で Webフォント（web-font.html）

和文Webフォントもありますが、今回は導入しやすい欧文Webフォントで説明します。

Google Fonts
https://fonts.google.com/


    <h1 class="webfonts">Company</h1>


    .webfonts {
      font-family: 'Roboto Slab', serif;
    }





----------
# レスポンシブ（responsive-html.html）

レスポンシブデザインとは、PC、タブレット、スマートフォンなどの色々なデバイスに最適化した表示を1つのHTMLファイルで対応できる方法です。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1522396939826_responsive1.png)

    <div class="responsive">
      <div class="left">レフトコンテンツ</div>
      <div class="right">ライトコンテンツ</div>
    </div>


[assets/css/responsive.css]


    .responsive {
      text-align: center;
      margin: 0 3%;
    }
    .responsive .left,
    .responsive .right {
      padding: 20px;
    }
    .responsive .left {
      background-color: orange;
    }
    .responsive .right {
      background-color: skyblue;
    }


## Viewport について

ブラウザでどのように見えるかを設定する為のタグです。
head内に記述します。

[Google - レスポンシブ ウェブデザインの基本](https://developers.google.com/web/fundamentals/design-and-ux/responsive/#set-the-viewport)


    <meta name="viewport" content="width=device-width, initial-scale=1">



## メディアクエリを使ってCSSを読み込む方法

**HTMLのlinkタグに記述（responsive-html.html）**


    <link rel="stylesheet" href="assets/css/style.css" media="(min-width: 960px)">


**CSS内に記述（responsive-css.html）**


    @media (max-width: 576px) { ... }


    @media (min-width: 768px) and (max-width: 992px) {...}




    .responsive {
      text-align: center;
      margin: 0 3%;
    }
    .responsive .left,
    .responsive .right {
      padding: 20px;
    }
    .responsive .left {
      background-color: orange;
    }
    .responsive .right {
      background-color: skyblue;
    }
    
    @media (min-width: 768px) {
      .responsive .left {
        background-color: palegreen;
      }
      .responsive .right {
        background-color: pink;
      }        
    }


**書き方ルール**

min-width → 最小の横幅が ◯◯px の時に ~
max-width → 最大の横幅が ◯◯px の時に ~

スマートフォン用のCSSから書いていくことをモバイルファースト、
デスクトップ用のCSSから書いていくことをデスクトップファーストといいます。

横並びのレイアウトがほとんど無いスマートフォンからCSSを書く事によって、冗長なコードにならない様にします。
 
 

**各デバイス用に設けたブレイクポイント**


- スマートフォン　　： 576px
- タブレット　　　　： 768px
- デスクトップ　　　： 992px
- 大画面デスクトップ： 1200px

参考：[Responsive breakpoints](https://getbootstrap.com/docs/4.0/layout/overview/#responsive-breakpoints)



![クスールサイトのブレークポイントは 768px の1つです](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1522627577175_responsive2.png)





    .responsive {
      text-align: center;
      margin: 0 3%;
    }
    @media (min-width: 576px) {
      .responsive {
        display: flex;
        justify-content: center;
      }
    }
    .responsive .left,
    .responsive .right {
      padding: 20px;
    }
    @media (min-width: 768px) {
      .responsive .left,
      .responsive .right {
        width: 200px;
        height: 200px;
        padding: 0;
      }
    }
    .responsive .left {
      background-color: orange;
    }
    .responsive .right {
      background-color: skyblue;
    }
    @media (min-width: 992px) {
      .responsive .left {
        background-color: palegreen;
      }
      .responsive .right {
        background-color: pink;
      }   
      .responsive .left,
      .responsive .right {
        width: 400px;
        height: 400px;
      }     
    }




参考：[The Ultimate Guide To iPhone Resolutions](https://www.paintcodeapp.com/news/ultimate-guide-to-iphone-resolutions)


※デバイスが縦長か横長で振り替わる


- portrait: 縦長の場合
- landscape: 横長の場合


    @media (orientation: portrait) { ... }
    @media (orientation: landscape) { ... }





