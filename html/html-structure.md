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

##  HTMLファイルを作成してみよう

### HTMLファイルの作り方

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>はじめまして</title>
    <meta name="description" content="サイトの概要">
  </head>
  <body>
    
  </body>
</html>
```

<br><br><br>

### ```<!DOCTYPE html>```

**文書がHTML5で作成されたものであることを宣言**

DOCTYPEの文字は大文字小文字どちらでも構いません。慣例で大文字にしている事が多いようです。

<br><br><br>

### ```<html>```

### HTML文書の内容が始まることを表す。文章全体を囲むタグ。
HTML要素は、HTMLドキュメントの **ルート（root / 基点）** であることを示す要素。

「lang="ja"」は、要素内で使用されている言語を表記する属性。
プログラムの自動翻訳機能はこの属性を見て判断しています。

<br><br><br>

### ```<head>```

#### サイト全般の情報（メタデータ）を記述する要素

サイトのタイトルや文字コード、ブラウザ上での見せ方制御、Facebookなどでシェアされた際に表示させる画像の指定などなど。
ブラウザで開いた際には表示されず、ソースコード上のみ確認する事ができます。

**headタグ内で使う主なタグたち**

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

### ```<meta charset="utf-8">```
コンピューター語を人間が読める言語（日本語など）に置き換える際の決まりごとです。<br>
※ ```<head>```の中には必須なのでこういったものがあるとだけ覚えておいてください。

#### 参考
■ 文字コードUTF-8とは〜世界でもっともポピュラーな文字コードとその仕組みを学ぼう

[https://qiita.com/pompom0c0/items/5c00a188aab744cfc918](https://qiita.com/pompom0c0/items/5c00a188aab744cfc918)

<br><br><br>

### <title>タグ、<meta name="description">タグ

下の画像はGoogleの検索結果の一覧ページです。

そこにタイトルとサイトの説明が表示される仕組みになっています。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-structure2.png)

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-structure3.png)

<br><br><br>

#### 参考
■ A free guide to ```<head>``` elements

[https://gethead.info/](https://gethead.info/)

■HTMLページのhead内に記述する要素の総まとめ

[http://coliss.com/articles/build-websites/operation/work/list-of-head-elements.html](http://coliss.com/articles/build-websites/operation/work/list-of-head-elements.html)

■もうmeta要素を迷わない！最低限入れるべきmeta要素のまとめ

[https://qiita.com/pompom0c0/items/5c00a188aab744cfc918](https://qiita.com/pompom0c0/items/5c00a188aab744cfc918)

<br><br><br>

### ```<body>```

#### 実際にブラウザに表示される文章の本体を記述する要素

ブラウザで見ているコンテンツを記述する場所です。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-structure4.png)

<br><br><br>

## HTML5タグを用いたセクショニングを

```<article>``` と ```<section>```

### ```<article>``` について

- その内容を取り出しても独立したコンテンツとして成り立つ場合に使用する。
（赤枠がarticle）

### ```<section>``` について

- 章や節など、意味的に関係のある要素をまとめる場合に使用する。
- タグの中に見出しタグ（h1 〜 h6）が1つ以上必要。
（緑枠がsection）


![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-tag3.png)
（黄色はaside）



![水色がnav、赤枠がarticle、緑枠がsection、黄枠はaside、青がp](https://laro.jp/wp-content/uploads/2019/11/lesson-html-tag4.png)  
※水色がnav、赤枠がarticle、緑枠がsection、黄枠はaside、青がp

<br><br><br>

## ```<div>``` と ```<span>``` を多用しすぎない事が大事です
サイトをコーディングしているとどうしても文章構造を付けられない（```<p>```などで囲めない）テキストがでてきます。
その場合は意味のないタグ（```<div>``` と ```<span>```）を付ける必要があるのですが、気を付けないと```<div>```ばかりになってしまうのでご注意ください。

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

<br><br><br>

## HTMLタグ付けの例

### サイトのヘッダー周りの実例
```html
<header>
  <h1>サイトの名前</h1>
  <nav>
    <ul>
      <li><a href="index.html">ホーム</a></li>
      <li><a href="about.html">アバウト</a></li>
      <li><a href="menu.html">メニュー</a></li>
      <li><a href="contact.html">お問い合わせ</a></li>
    </ul>
  </nav>
</header>
```

#### 解説
* ```<header>``` サイトのヘッダーを表しています。
* そのタグの中にそのサイトの大見出し ```<h1>```を書いています。
* ```<ul>``` がこのサイトのナビゲーション```<nav>```だと表しています。
* ナビゲーションメニュー1〜4をクリック```<a>```できるようにしています。



### メインコンテンツ周りの例
```html
<main>
  <article>
    <section>
      <h2>コンテンツAの名前</h2>
      <p>コンテンツAの文章が入ります。</p>
    </section>
    <section>
      <h2>コンテンツBの名前</h2>
      <p>コンテンツBの文章が入ります。</p>
      <ul>
        <li>コンテンツBの箇条1</li>
        <li>コンテンツBの箇条2</li>
        <li>コンテンツBの箇条3</li>
      </ul>
    </section>
    <section>
      <h2>コンテンツCの名前</h2>
      <p>コンテンツCの文章が入ります。</p>
      <div><img src="コンテンツC.jpg" alt=""></div>
    </section>
  </article>
  <aside>ここは広告バナーです</aside>
</main>
```

#### 解説
* ```<main>``` そのページのメインコンテンツを表しています。
* ```<article>``` このページの記事を表しています。
* ```<section>``` それぞれのコンテンツの塊（章）を表しています。
* ```<h2>``` h1タグの次に重要な中見出しを表しています。
* ```<div>``` 意味合いの薄い画像や文章は、```<div>```で囲みます。
* ```<img src="コンテンツC.jpg" alt="">``` 画像を表示できます。
* ```<aside>``` このページの記事外に広告など載せる場合の例です。


### フッター周りの例
```html
<footer>
  <address>東京都世田谷区世田谷1-1-1</address>
  <small>Copyright 2019 watamura.</small>
</footer>
```
#### 解説
* ```<footer>``` そのページのフッターを表しています。
* ```<address>``` 今回は住所を記載していますが、電話番号やメールアドレスも可能です。
* ```<small>``` Copyrightという著作権情報を記載しています。

<br><br><br>

---

<br><br><br>

### HTMLには厳格な決まりはありません
コーダーの文章構造の解釈や組織によって、どんなルールで書くかはそれぞれなので、上記は参考までに覚えておいてください。
人によっては```<p>```を使い、別の人は```<div>```で囲む、といった感じです。

