# 2. CSS基礎編 1


# CSSとは


## Cascading Style Sheetsの略

HTMLが文章構造を指定する言語であるのに対して、
CSSはそのHTML文章のレイアウトや装飾などの見た目を指定する為の言語。



![](https://d2mxuefqeaa7sj.cloudfront.net/s_3066FA23A18E1433BC4D48A1112B9F0C6A766C9E0917C880D3A50377E5D58EB4_1520566501261_HTML.png)



![](https://d2mxuefqeaa7sj.cloudfront.net/s_3066FA23A18E1433BC4D48A1112B9F0C6A766C9E0917C880D3A50377E5D58EB4_1520567145555_CSS.png)



----------
# CSSの基本的な書き方


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1520926483939_CSS.png)



- セレクタ　：　適用する対象　　　　　← どれ
- プロパティ：　スタイルの種類　　　　← 何を
- 値　　　　：　適用させたい結果　　　← どうするか


- プロパティと値は波括弧で囲う
- プロパティと値はコロン（：）でつないでセミコロン（；）で終わる



    p {
    　color: red;
    　font-weight: bold;
    　margin-left: 20px;
    }

↓

    pタグの {
    　色を: 赤にする;
    　太さを: 太くする;
    　左側の隙間を: 20pxにする;
    }



----------


# 記述する場所について


## HTMLタグに直接記述する


    <p style="color: red;">この文字を赤にしたい。</p>


## head要素内に記述する


    <!DOCTYPE html>
    <html lang="ja">
      <head>
        <meta charset="utf-8">
        <title>セレクタの練習1</title>
        <style>
          p {
          　color: red;
          }
        </style>
      </head>
      <body>
      　<p>この文字を赤にしたい。</p>
      </body>
    </html>


**コメントの書き方**


    /* コメントを書いて分かりやすいスタイルシートを書こう */
    
    /*
        コメントは複数行でも記述できます。
        説明やメッセージなどを残せます。
    */


## 外部ファイルに記述する
    <!DOCTYPE html>
    <html lang="ja">
      <head>
        <meta charset="utf-8">
        <title>セレクタの練習1</title>
        <link rel="stylesheet" href="style.css">
      </head>
      <body>
      　<p>この文字を赤にしたい。。</p>
      </body>
    </html>


    /* style.css の中身 */
    p {
    　color: red;
    }



----------
# セレクタについて
    <!DOCTYPE html>
    <html lang="ja">
      <head>
        <meta charset="utf-8">
        <title>セレクタの練習</title>
        <style>
        　ここにスタイルシートを書く
        </style>
      </head>
      <body>
        <div>
          <p class="hello">こんにちは</p>
        </div>
        
        <p style="color: pink;">こんばんは</p>
    
        <p id="id-selector">はじめまして</p>
    
        <p class="goodbye">さようなら</p>
    
        <div class="hello-wrapper">
          <div class="hello">こんにちは</div>
        </div>
      </body>
    </html>



## 代表的なセレクタ一覧　（selector1.html）


1. **全称セレクタ**
    * {
    　color: blue;
    }


2. **インラインStyle属性**
    <p style="color: red;">インラインスタイル</p>


3. **タグセレクタ**

p タグの文字色を赤にしてください。


    p {
     color: red;
    }


4. **IDセレクタ**

id-selector のIDが付いた要素の文字色を水色にしてください。


    <div id="id-selector">IDセレクタで文字の色を変える</div>


    #id-selector {
     color: skyblue;
    }

※ id名は同じ要素に対して複数のid名を指定することはできません。

    <div id="test test2">これは無効です</div>



5. **クラスセレクタ**

hello-wrapper クラスがついた要素の文字色をオレンジ色にしてください。


    .hello-wrapper {
     color: orange;
    }




6. **複数一括セレクタ**

goodbye クラスとhello クラスが付いた要素の文字色をグレーにしてください。


    .goodbye, .hello {
     color: gray;
    }



7. **子孫セレクタ**
    .hello-wrapper .hello {
     color: tan;
    }


**クラスの付け方のルールや注意点**


- 英字大文字小文字は区別される。
- 日本語もOK（だけど使わない）
- 使用できる記号は「 - ハイフン」と「 _ アンダーバー」
- 数字もOKだが、頭にはNG


    .hello {...}
    .Hello {...}
    
    .こんにちは {...}
    
    .hello-goodbye {...}
    .hello_goodbye {...}
    
    .hello8 {...}
    .8hello {...} /* NG */



## 他にもあるセレクタ　（selector2.html）


    <section class="news-area">
      <ul class="news-area-main">
        <li>メインニュース1</li>
        <li>メインニュース2</li>
        <li>メインニュース3</li>
      </ul>
      <div>
        <ul class="news-area-sub">
          <li>サブニュース1</li>
          <li>サブニュース2</li>
          <li>サブニュース3</li>
        </ul>
      </div>
    </section>


8. **子セレクタ**


    /* よくない例 */
    .news-area ul li {
     color: #skyblue;
    }


    .news-area > ul li {
     color: #skyblue;
    }


9. **隣接セレクタ**


    .news-area .news-area-main li + li {
     background-color: pink;
    }



## まだまだあるセレクタ　（selector3.html）
    <ul class="main-menu">
     <li><a href="#">メニュー1</a></li>
     <li><a href="#">メニュー2</a></li>
     <li><a href="#">メニュー3</a></li>
     <li><a href="#">メニュー4</a></li>
     <li><a href="#">メニュー5</a></li>
     <li><a href="#">メニュー6</a></li>
     <li><a href="#">メニュー7</a></li>
     <li><a href="#">メニュー8</a></li>
    </ul>


10. **擬似クラス**


- hover　　　　　 → カーソルが乗っている要素


- first-child　　　 → 要素内の最初の子要素
    - ■□□□□□□□□
- last-child　　　 → 要素内の最後の子要素
    - □□□□□□□□■
- nth-child(n)　　 → 要素内のn番目の子要素
    - □□■□□□□□
- nth-child(odd)　→ 要素内の奇数の子要素
    - ■□■□■□■□
- nth-child(even)  → 要素内の偶数の子要素
    - □■□■□■□■
- nth-child(n + 5) → 5個目以降のliを指定する場合
    - □□□□■■■■
- nth-child(-n + 5) → 5個目までを指定する場合
    - ■■■■■□□□



    /* カーソルが乗っている要素 */
    .main-menu li a:hover {
     background-color: red;
     text-decoration: none;
    }
    
    /* 最初の要素 */
    .main-menu li:first-child {
     background-color:#faa;
    }
    /* n番目の要素 */
    .main-menu li:nth-child(2), .main-menu li:nth-child(3) {
     background-color:#afa;
    }
    /* 最後の要素 */
    .main-menu li:last-child {
     background-color: #aaf;
    }
    /* 奇数の要素 */
    .main-menu li:nth-child(odd) {
     background-color:#faf;
    }
    /* 偶数の要素 */
    .main-menu li:nth-child(even) {
     background-color:#ffa;
    }
    /* 3の倍数の要素 */
    .main-menu li:nth-child(3n) {
     background-color:#aff;
    }
    /* 3の倍数プラス1の要素 */
    .main-menu li:nth-child(3n+1) {
     background-color:#aff;
    }

参考サイト： http://www.bad-company.jp/nth-child/



## 詳細度

セレクタには詳細度というものがあり、セレクタの設定によって詳細度が変化し、セレクタの詳細度によって優先されるスタイルが上書きされます。


    <div>
      <p class="menu">こんにちは</p>
    </div>


    div .menu {
     color: orange;
    }
    div p {
     color: skyblue;
    }
    p {
      color: palegreen;
    }


| **指定方法**   | **例**                  | **点数** |
| ---------- | ---------------------- | ------ |
| タグのstyle属性 | style="color: orange;" | 1000点  |
| ID         | ＃hoge                  | 100点   |
| クラス        | .hoge                  | 10点    |
| 要素名        | ul                     | 1点     |
| 擬似クラス      | :first-child           | 1点     |
| 全称セレクタ     | *                      | 0点     |


**計算例**

| **例**             | **計算**                               | **合計点** |
| ----------------- | ------------------------------------ | ------- |
| style=""          | 1000(style属性)                        | 1000点   |
| ＃hoge             | 100(ID属性)                            | 100点    |
| li.color.label    | 1(要素名) + 10(クラス属性) + 10(クラス属性)       | 21点     |
| table tr td.color | 1(要素名) + 1(要素名) + 1(要素名) + 10(クラス属性) | 13点     |
| h1 div + span     | 1(要素名) + 1(要素名) + 1(要素名)             | 3点      |
| li:last-child     | 1(要素名) + 1(擬似クラス)                    | 2点      |


※ただし、クラスを10個以上付ければID属性の詳細度を超える訳ではないので注意してください。
（10個以上は点数は無視されると考えて下さい）



----------
# プロパティについて（properties1html）


## 文字の色・大きさ・太さ


    <div class="text">文字の色・大きさ・太さ</div>


    .text {
      color: #40dce8; /* rgba(64, 220, 232, 100) */
      font-size: 16px; /* px, em, %, rem */
      font-weight: normal; /* normal, bold, 400, 800 */
      text-decoration: underline; /* none, underline */
    }


それぞれの初期値（デフォルト）は、#000000、16px、normal、none


## カラーコードについて

[カラーコード 早見表](http://www5.plala.or.jp/vaio0630/hp/c_code.htm)

**16進数のカラーコード**

黒← 　0, 1, 2, 3, 4, 5, 6, 7, 8, 9, a, b, c, d, e, f　→白


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521170368133_.png)


**rgba**

黒← 　0 〜 255　→白
透明← 0 〜 1 →不透明

![](https://paper-attachments.dropbox.com/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1562395570706_rgba.png)




## 単位について（font-size.html）

**px（ピクセル）**

- 絶対値
- ユーザーがブラウザからそのサイズを変更する事ができない

**em（エム）**

- 相対値
- 親要素のフォントサイズの倍率


    <div class="px">pxを使ったフォントサイズ</div>
    <div class="em">emを使ったフォントサイズ</div>
    <div class="percent-wrapper"><p class="percent">パーセントを使ったフォントサイズ</p></div>
    <div class="rem">remを使ったフォントサイズ</div>


    .px {
      font-size: 16px;
    }
    .em {
      font-size: 0.5em;
    }

**%（パーセント）**

- 相対値
- 親要素のフォントサイズの倍率


    .percent-wrapper {
     font-size: 75%; /* 12px */
    }
    .percent {
      font-size: 200%; /* 12px * 2 = 24px */
    }


[PXtoEM.com PX to EM conversion made simple.](http://pxtoem.com/)


**rem（レム / ルートエム）**

- 相対値
- emと同じような考え方だが、ルート(htmlタグ)に対する割合のサイズ


    html {
     font-size: 100%; /* 16px */
    }
    .rem {
      font-size: 3rem; /* 16px * 3(rem) = 48px */
    }

％ や em と同様に相対値ですが、ルート（html）の値を参照するため、計算が楽でメンテナンス性にも優れている。


    <h1 class="title">ヘッダータイトル</h1>
    <p class="description">吾輩は猫である。名前はまだ無い。どこで生れたかとんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれ</p>


    html {
      font-size: 10px;
    }
    body {
     font-size: 1.4rem;
    }
    .title {
     font-size: 1.6rem;
    }



## 文字を左右中央に寄せる


    <div class="text-align">文字を左右中央に寄せる</div>


    .text-align {
      text-align: center; /* 初期値は left */
    }



## 行間を指定する


    <div class="line-height">行間を指定する</div>


    .line-height {
      line-height: 2;
    }


- 文字サイズの倍率を指定
- 単位は付けずに記述することが一般的


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522845201939_.png)




![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1521177549564_2.png)




