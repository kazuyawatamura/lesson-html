# HTMLの構造を知ろう

## HTMLタグの基本的な書き方

HTMLとは、テキストにタグを付けて文章構造を与えるための言語です。  
タグをつけたテキストは、それぞれ役割を持った「要素」となり、その集合体がWebサイトを作っています。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-structure1.png)

上の例は「pタグ」といいます。  
pとは、Paragraph（パラグラフ）=文節・段落という意味で、このpタグで囲まれたテキストは段落という意味になります。  
pタグの他にもいろいろなタグの種類があるので、調べて勉強してみましょう。  

<br><br><br>

### タグを書く際のルール
- 「<」（小なり）と「>」（大なり）でタグ名を囲む
- 開始タグと終了タグがある
- 終了タグはタグ名の前に「/」（スラッシュ）を付ける
- 開始タグ単独で記述するタグもある（後述します）

<br><br><br>

##  HTMLファイルを作ってタグを覚えよう

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <title>はじめまして</title>
  </head>
  <body>
    
  </body>
</html>
```

1. ```<!DOCTYPE html>``` 文書がHTML5で作成されたものであることを宣言
1. ```<html>``` HTML文書の内容が始まることを表すタグ
  - 「lang="ja"」は、要素内で使用されている言語を表記する属性
  - プログラムの自動翻訳機能はこの属性を見て判断しています
1. ```<head>``` サイト全般の情報（メタデータ）を記述する要素
  - サイトのタイトルや文字コード、ブラウザ上での見せ方制御、Facebookなどでシェアされた際に表示させる画像の指定などなど
  - ブラウザで開いた際には表示されず、ソースコード上のみ確認する事ができます
1. ```<body>``` ブラウザに表示される文章（コンテンツ）を記述する要素

<br><br><br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-structure4.png)

<br><br><br>

### headタグ内で使う主なタグたち

- ```<meta>```
- ```<link>```
- ```<script>```

```html
<!-- 文字コードの指定（コンピュータ内部で文字を表示させるためのルール） -->
<meta charset="utf-8">
<!-- サイトのタイトル -->
<title>サンプルリファレンスサイト</title>
<!-- サイトの説明文 -->
<meta name="description" content="サイトの概要">
```

<br><br><br>

#### <meta charset="utf-8"> タグ
コンピューター語を人間が読める言語（日本語など）に置き換える際の決まりごとです。  
※ ```<head>```の中には必須なのでこういったものがあるとだけ覚えておいてください。

<br><br><br>

#### <title> タグ、 <meta name="description"> タグ

下の画像はGoogleの検索結果の一覧ページです。  

そこにタイトルとサイトの説明が表示される仕組みになっています。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-structure2.png)

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-structure3.png)

<br><br><br>

#### 参考
■ A free guide to ```<head>``` elements
[https://gethead.info/](https://gethead.info/)
  
■もうmeta要素を迷わない！最低限入れるべきmeta要素のまとめ
[https://qiita.com/pompom0c0/items/5c00a188aab744cfc918](https://qiita.com/pompom0c0/items/5c00a188aab744cfc918)

<br><br><br>

## body内に記述する主要なHTMLタグを書いてみよう

```<body>``` タグの中に下記のタグを書いてみましょう。

```html
<header>
  サイトやコンテンツのヘッダー
</header>

<nav>
  ナビゲーション、メニュー
</nav>

<main>
  ページ固有のコンテンツ/各ページにつき1回しか使用できない
</main>

<article>
  自己完結した内容。見出しタグ
</article>

<section>
  章、コンテンツごとの固まり

  <h1>大見出し、Headerの略</h1>
  <h2>中見出し、Headerの略</h2>
  <h3>小見出し、Headerの略</h3>
  <h6>小見出し、Headerの略</h6>
</section>

<aside>余談・補足情報、広告なども</aside>

<footer>
  関連文書へのリンク、著作権などの情報
</footer>

<p>
  段落・本文、Paragraphの略
</p>

<em>本文内（インライン）での強調</em>
<strong>本文内（インライン）での強い強調</strong>

<a href="https://www.yahoo.co.jp/">リンク、Ankerの略</a>

<img src="https://picsum.photos/300/300" alt="ダミー画像">
<!-- 画像、閉じタグ無し -->

<ul>
  <li>箇条、Unodered Listの略</li>
  <li>箇条、Unodered Listの略</li>
</ul>
<ol>
  <li>箇条、Ordered Listの略</li>
  <li>箇条、Ordered Listの略</li>
</ol>

<small>免責・警告・法的規制・著作権・ライセンス要件などの注釈</small>

<time datetime="2020-05-20">2020年5月20日</time>
<!-- 日時 -->

<address>
  <a href="mailto:user@example.com">user@example.com</a>
</address>

<div>意味のないブロック要素、スタイリング用</div>

<span>意味のないインライン要素、スタイリング用</span>

<br>
<!-- 改行、Breakの略、閉じタグ無し -->
```

<br><br><br>

## タグの属性

HTMLタグはその種類に応じて設定を付加できます。  
この設定のことを「属性」、設定の内容のことを「属性値」といいます。  
  
付加することのできる属性はタグごとに異なっています。  
たとえばリンクを定義する```<a>```タグには、リンク先を指定するhref属性を付加し、属性値としてリンク先のURLなどを設定できます。

### ```<a>``` タグの属性と属性値

```<a>``` タグは、主に他のページや他のWebサイトに移動するためのタグです。

- **href** とは、クリックしたら飛び先の指定ができる属性です。
- リンクを設定したい文字を ```<a>``` タグで囲んでください。

<br>

```<a href="~~"> **ここにリンクしたいテキストを書きます** </a>```


![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-tag1.png)


### <img> タグの属性と属性値

```img``` タグは、画像を表示させるタグです。

- **src** とは、表示したい画像の場所を示す属性です。
- **alt** とは、画像がどのような画像なのか、をテキストで説明する属性です。目の見えない方が使う音声ブラウザーなどで読まれます。

<br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-tag2.png)

<br><br><br>

## ブラウザには表示させないコメントを書くことができます

```html
<!-- コメントを書くことができます。これはブラウザでは表示せずコード上に説明コメントを残すことができます -->
```

```html
<!-- 
  このように誰がみても分かりやすいように注釈いれるようにコメントができます
  以下はフッターです。住所とコピーライトを書いています
 -->

<footer>
  <address>東京都世田谷区世田谷1-1-1</address>
  <small>Copyright 2019 watamura.</small>
</footer>
```