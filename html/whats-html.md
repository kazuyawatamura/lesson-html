# HTMLとは何か？


## Webサイトが表示される仕組み


まず、ブラウザ（SafariやGoogle Chromeなど）のアドレスバーにURL（http://~~）を打ち込むとWebサイトが表示されると思います。
そしてインターネット上のサーバーに保存されているHTMLファイルや画像にアクセスし、ブラウザがそのデータ（HTMLやCSS）をお使いのPCにダウンロードします。
それらの**HTMLやCSSといったコンピューター言語をブラウザが解読し**人間に見れるように表示してくれます。

それがいつも見ているWebサイトの見た目を表示し整えてくれる仕組みです。



![](https://laro.jp/lesson/images/lesson-html-about1.png)

<br><br><br>

### HTMLとはWEBサイトを構成する基本的で大事な言語

それでは適当なWebサイトのHTML（ブラウザではソースという表記）を見てみましょう。

ブラウザの種類によってソースの見方が違うので、下記を参考にしてください。

* Google Chrome：「表示」→「開発/管理」→「ソースを表示」
* Safari：環境設定を変更してから「開発」→「ページのソースを表示」

そうすると下記のようにソースがびっしりと並んだ画面が表示されるかと思います。
ソースコードは、いろいろなWebサイトで見ることができるので、いくつか試しに見てみるとよいでしょう。

![これがHTML](https://laro.jp/lesson/images/lesson-html-about2.png)


----------

<br><br><br>

# Webサイトを構成するファイル

<br><br><br>

## HTML、CSS、JavaScriptの役割

<br><br><br>

### HTML（Hyper Text Markup Language）


- 役割：**文章構造の定義するための言語**
    - 「この画像は、ロゴです」
    - 「このリストは、このサイトのメニューです。」
    - 「このテキストは、この段落のタイトルです」
    - etc…


![](https://laro.jp/lesson/images/lesson-html-about3.png)


検索ロボット（GoogleBotなど）が文章構造を解析・理解して、WEBサイトの内容を理解して検索結果に反映させる事もあります。

そもそもハイパーテキストというのは何かと簡単に説明すると「リンク」です。
それぞれ別のHTMLとHTMLをリンクでWebサイトを繋げて広げていくというのがハイパーテキストの概念です。

<br><br><br>

#### HTMLはプログラミング言語か

正確にいうとHTMLとCSSはプログラミング言語ではありません。
プログラミング言語とはコンピューターに演算処理（計算）をさせていますが、HTMLは前述の通り文章構造を定義するものなのでまったく違うものなのです。

<br><br><br>

### CSS（Cascading Style Sheets）


- 役割：**レイアウトや色などを指定する装飾**
    - 「見出しにアイコンを付けましょう」
    - 「線で囲みましょう」
    - 「この文字を大きくしましょう」
    - etc…


![](https://laro.jp/lesson/images/lesson-html-about4.png)


前述したHTMLで構造化したテキストを、人間が読みやすく整理したり文字の大きさを変更したり色を付けたりデザインができます。


<br><br><br>

### JavaScript


- 役割：**動き・インタラクティブ**
    - 左右に流れるスライドショー
    - スマホサイトの右上にある三本線のメニューボタン（ハンバーガーメニューという名称）の開閉アニメーション
    - etc…


![https://ensemble-magazine.com/](https://laro.jp/lesson/images/lesson-html-about5.gif)

--

![https://ensemble-magazine.com/](https://laro.jp/lesson/images/lesson-html-about6.gif)


HTMLやCSSと連携して、ユーザーの目に留まりやすいアニメーション（インタラクション）を制作する事ができます。
JavaScriptを書かずにWebサイトはできますが、アニメーションさせたりユーザーに反応（※）を返す手段としてJavaScriptはよく用いられます。

※ボタンをクリックした際のメニューの開閉やスライドショー、ページトップへ戻るボタンなど