# 5. jQuery


# ハンバーガーメニューの開閉


![こんなハンバーガーメニューを作っていくます。](https://d2mxuefqeaa7sj.cloudfront.net/s_CB2B46DB209395B6355AEEBA793F6C1CF030B75B63E768067C77F38A1E246B1B_1522402042763_Kapture+2018-03-30+at+18.27.03.gif)


https://jquery.com/
jQueryの最新版をダウンロードします。 `./assets/js/`  に保存してください。



    <nav class="global-nav">
      <div class="toggle-btn"><img src="./assets/images/menu.svg"></div>
      <ul>
        <li><a href="#">メニュー1</a></li>
        <li><a href="#">メニュー2</a></li>
        <li><a href="#">メニュー3</a></li>
        <li><a href="#">メニュー4</a></li>
      </ul>
    </nav>


    .toggle-btn {
      position: fixed;
      top: 17px;
      right: 15px;
      width: 30px;
      height: 30px;
      z-index: 2;
    }
    .global-nav ul {
      display: none;
      position: fixed;
      top: 0;
      width: 100%;
      height: 100vh;
      background-color: #eeeeee;
      z-index: 1;
    }
    .global-nav li a {
      display: block;
      padding: 30px 0;
      text-align: center;
      text-decoration: none;
      color:#333333;
      background-color: #ffffff;
      border-bottom: 1px solid #eeeeee;
    }


    <script src="./assets/js/jquery-3.2.1.min.js"></script>


    <script>
      $(document).ready(function(){
        $('.toggle-btn').on('click', function(){
          console.log('クリックされました。');
          $('.global-nav ul').slideToggle();
        });
      });
    </script>



## jQueryの基本


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CB2B46DB209395B6355AEEBA793F6C1CF030B75B63E768067C77F38A1E246B1B_1522629777868_jquery1.png)



![](https://d2mxuefqeaa7sj.cloudfront.net/s_CB2B46DB209395B6355AEEBA793F6C1CF030B75B63E768067C77F38A1E246B1B_1522629785917_jquery2.png)



    console.log('出力されました');

コンソール画面に任意のコメントなどを表示させることによって、プログラムが正常に動作しているかどうかなどの確認する事ができます。



    $('.global-nav ul').slideToggle();

指定された要素（今回は  `.global-nav ul` ）に対して、表示されている時は隠し、隠れている時は表示する。







----------
# スクロールでfixed



    <header class="header">
      ヘッダ
    </header>
    <nav class="global-nav">
      グローバルメニュー
    </nav>
    <main class="maincontents">
      メインコンテンツ
    </main>


    .header {
      height: 300px;
      background-color: grey;
    }
    .global-nav {
      height: 100px;
      background-color: palegreen;
      transition: 0.2s ease-out;
    }
    .maincontents {
      height: 3000px;
      background-color: royalblue;
    }
    .fixed-menu {
      position: fixed;
      top: 0;
      width: 100%;
      height: 50px;
    }
    .fixed-menu + .maincontents {
      margin-top: 50px;
    }



    $(window).scroll(function(){
      // スクロールのピクセル数を取得する
      var pixel = $(window).scrollTop();
      console.log(pixel);
      // スクロールが300pxを超えたら、fixed-menuクラスを付与する
      if(pixel > 300){
        $('.global-nav').addClass('fixed-menu');
      } else {
        $('.global-nav').removeClass('fixed-menu');
      }
    });



----------


# Slickでスライド


    <link rel="stylesheet" href="./assets/slick/slick.css">
    <link rel="stylesheet" href="./assets/slick/slick-theme.css">
    <script src="./assets/js/jquery-3.3.1.min.js"></script>
    <script src="./assets/slick/slick.min.js"></script>


    <ul class="slider">
      <li><a href="#"><img src="./assets/images/mv01_pc.jpg"></a></li>
      <li><a href="#"><img src="./assets/images/mv02_pc.jpg"></a></li>
      <li><a href="#"><img src="./assets/images/mv03_pc.jpg"></a></li>
      <li><a href="#"><img src="./assets/images/mv04_pc.jpg"></a></li>
      <li><a href="#"><img src="./assets/images/mv05_pc.jpg"></a></li>
    </ul>


    /*左右の矢印の色を変える*/
    .slick-prev:before,
    .slick-next:before {
      color: #000;
    }
    /*左右の矢印の位置を変える*/
    .slick-next {
      right: 20px;
      z-index: 99;
    }
    .slick-prev {
      left: 15px;
      z-index: 100;
    }
    /*スライド数のドットの色を変える*/
    .slick-dots li.slick-active button:before,
    .slick-dots li button:before {
      color: #000;
    }
    /*スライド画像の横幅可変*/
    img {
      max-width: 100%;
      height: auto;
      /*width: 100%;*/
    }
    .slider {
      width: 1000px;
      margin: 0 auto;
    }


    $(document).ready(function() {
      $('.slider').slick({
        autoplay:true
      });
      // 画面の幅に合わせて読み込む画像をかえる
      if ( $(window).width() < 768 ) {
        $('.slider img').each(function(){
          var spURL = $(this).attr('src').replace('_pc', '_sp');
          $(this).attr('src', spURL);
        });
      }
    });



----------


# jQuery.inview と animate.css でCSSアニメーション

https://codepen.io/cotton/pen/aabmJW


