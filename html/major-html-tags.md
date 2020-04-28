
# 主要なHTMLタグを書いてみよう

```html
<h1> ~ <h6>　（見出し）
<p>　（段落・本文）
<strong>, <em>　（本文の強調）
<a href="xxx">　（リンク）
<img src="xxx">　（画像）
<ul>, <ol>　（箇条）
<li> （リスト）
<time> （日時）
<header>　（サイトやコンテンツのヘッダー）
<footer>　（関連文書へのリンク、著作権などの情報）
<nav>　（ナビゲーション）
<main> （ページ固有のコンテンツ/各ページにつき1回しか使用できない）
<article>　（自己完結した内容、見出しタグ（h1〜h6）は必須ではない）
<section>　（章、コンテンツごとの固まり/見出しタグが必要）
<aside>　（余談・補足情報、広告なども）
<small>　（免責・警告・法的規制・著作権・ライセンス要件などの注釈）
<address>　（メアド・住所・電話番号等連絡をとるために必要な情報）
<div>　（意味の無いブロック要素）
<span>　（意味の無いインライン要素）
<br> （改行）
```

<br><br><br>

# 書いて覚えよう

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>HTML基礎</title>
  </head>
  <body>
  <!-- カッコの中のテキストをタグで囲んでみましょう -->
  </body>
</html>
```

上述のHTMLをコピーしてhtmlファイルを作って下記のタグを書いてみましょう。

- ```<header>```（サイトやコンテンツのヘッダー）
- ```<footer>```（関連文書へのリンク、著作権などの情報）
- ```<nav>```（ナビゲーション）
- ```<main>```（ページ固有のコンテンツ/各ページにつき1回しか使用できない）
  - ```<article>```（自己完結した内容。見出しタグ（h1〜h6）は必要でない）
  - ```<section>```（章、コンテンツごとの固まり。見出しタグが必要）
  - ```<h1> ~ <h6>```（見出し、Headerの略）
  - ```<p>```（段落・本文、Paragraphの略）
  - ```<strong>, <em>```（本文の強調）
  - ```<a href="xxx">```（リンク、Ankerの略）
  - ```<img src="xxx" alt="">```（画像）
  - ```<ul>, <ol>```（箇条、Unodered ListとOrdered Listの略）
  - ```<li>```（リスト）
  - ```<time>```（日時）
- ```<aside>```（余談・補足情報、広告なども）
- ```<small>```（免責・警告・法的規制・著作権・ライセンス要件などの注釈）
- ```<address>```（メアド・住所・電話番号等連絡をとるために必要な情報）
- ```<div>```（意味のないブロック要素）
- ```<span>```（意味のないインライン要素）
- ```<br>```（改行、Breakの略）

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

```<a href="~~">``` **ここにリンクしたいテキストを書きます** ```</a>```


![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-tag1.png)


### ```<img>``` タグの属性と属性値

```img```タグは、画像を表示させるタグです。

- **src** とは、表示したい画像の場所を示す属性です。
- **alt** とは、画像がどのような画像なのか、をテキストで説明する属性です。目の見えない方が使う音声ブラウザーなどで読まれます。

![](https://laro.jp/wp-content/uploads/2019/11/lesson-html-tag2.png)


<br><br><br>

## タグの入れ子（ネスト）

HTMLタグは「入れ子（ネスト）」といってタグの中にタグを書くことができます。
文章構造によっては、何重にもタグの入れ子をして文章構造を整えていくこともあります。

```html
<p>
  HTMLは、ハイパーテキストを記述するための<strong>マークアップ言語</strong>です。
</p>

<section>
  <h1>これは大見出しです</h1>
</section>
```

また、リストタグのように決められたタグの中でしか入れ子できないタグもあります。
下記のリストタグ ```<li>``` は、```<ul>``` か ```<ol>``` の中でしか入れ子にすることはできません。

```html
<!-- 順不同リスト -->
<ul>
  <li>リスト</li>
  <li>リスト</li>
  <li>リスト</li>
</ul>
<!-- 順序付きリスト -->
<ol>
  <li>リスト</li>
  <li>リスト</li>
  <li>リスト</li>
</ol>

<!-- リストの入れ子 -->
<ul>
  <li>リスト</li>
  <li>リスト</li>
  <li>
    <p>テキスト</p>
    <ol>
      <li>リスト</li>
      <li>リスト</li>
      <li>リスト</li>
      <li>リスト</li>
    </ol>
  </li>
</ul>
```
#### 参考
[https://about.yahoo.co.jp/common/terms/chapter1/](https://about.yahoo.co.jp/common/terms/chapter1/)


### 要素の分類（コンテンツモデル）
要素の分類（コンテンツモデル）とは「その要素にはどのカテゴリーのコンテンツを入れていいか」を決めているルールです。

HTMLを勉強し始めの頃は、タグの入れ子のルールが分かりづらいと思います。
ここではNG例とOK例をいくつか載せています。おおざっぱで構いませんので感覚を掴んでみてください。

```html
<!-- NG -->
<p>
  <h1>ヘッドライン</h1>
</p>
<!-- OK -->
<h1>ヘッドライン</h1>
```
→ 文章の中に見出しは入りません。h1タグをpタグ内から出してあげましょう。



```html
<!-- NG -->
<p>
  <div>pタグにdivは入れられない</div>
</p>
<p>
  <p>pタグにpは入れられない</p>
</p>

<!-- OK -->
<p>
  <span>pタグにspanは入れられる</span>
</p>
```
→ HTMLの仕様で、pタグの中には、aタグ・imgタグ・spanタグなどのインライン要素を入れることができます。
最初から覚える必要はないのでパターンとして覚えておいてください。

```html
<!-- NG -->
<article>
  <li>リスト</li>
  <li>リスト</li>
  <li>リスト</li>
</article>

<!-- OK -->
<article>
  <ul>
    <li>リスト</li>
    <li>リスト</li>
    <li>リスト</li>
  </ul>
</article>
```
→ liタグを囲めるのは、ulタグかolタグのみです

### 要素ごとのタグの入れ子ルール

要素ごとの入れ子ルールをよく使うタグに絞って一覧にしました。

#### divタグ：構造・レイアウト

divタグは、ほぼすべてのタグを入れ子にできます。

```html
a / article / aside / blockquote / br / button / div / dl / em / figure / footer / form / h1 / h2 / h3 / h4 / h5 / h6 / header / hgroup / hr / i / iframe / img / input / label / main / nav / ol / p / picture / pre / script / section / select / small / span / strong / svg / table / template / textarea / time / ul / video など
```

#### spanタグ：構造・レイアウト

spanタグは、同じインライン要素のタグを入れ子にできます（厳密には違いますが左記の通り覚えておいて結構です）

```html
a / br / button / data / em / i / iframe / img / input / label /picture / select / small / span / strong / svg / textarea / time / video など
```

#### h1〜h6タグ：見出し、pタグ：段落

上記のspanと同様に同じインライン要素のタグを入れ子にできると覚えておきましょう

```html
a / br / button / data / em / i / iframe / img / input / label /picture / select / small / span / strong / svg / textarea / time / video など
```

#### ul / olタグ：リスト定義

ulもolタグのどちらも基本的には、入れ子できるのはliタグのみです。

```html
li
```

#### liタグ：リスト定義（子要素）

divのように多くのタグを入れ子にできる万能なタグです。
上記の「リストの入れ子」のように階層構造にもできます。

```html
a / article / aside / blockquote / br / button / div / dl / em / figure / footer / form / h1 / h2 / h3 / h4 / h5 / h6 / header / hgroup / hr / i / iframe / img / input / label / main / nav / ol / p / picture / pre / script / section / select / small / span / strong / svg / table / template / textarea / time / ul / video
```

ただ、ulタグの直下にulタグを入れることはできないのでliタグの中にulタグかolタグを入れる必要があります。
例

```html
<!-- NG -->
<ul>
  <li>リスト</li>
  <li>リスト</li>
  <ul>
    <li>リスト</li>
    <li>リスト</li>
    <li>リスト</li>
    <li>リスト</li>
  </ul>
</ul>

<!-- OK -->
<ul>
  <li>リスト</li>
  <li>リスト</li>
  <li> ← これが必要
    <ul>
      <li>リスト</li>
      <li>リスト</li>
      <li>リスト</li>
      <li>リスト</li>
    </ul>
  </li>
</ul>
```

#### html5の入れ子タグのチートシート

HTML5 入れ子チートシート

[https://yoshikawaweb.com/element/](https://yoshikawaweb.com/element/)



### 開始タグと閉じタグの位置を合わせましょう

下記は間違っています。どこが違うかわかりますか？

```html
<p>HTMLは、ハイパーテキストを記述するための<strong>マークアップ言語</p>です。</strong>
```
  
  
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>

正解はこちらです。
答え：strongタグとpタグの終了タグの位置が変わっています。

```html
<p>HTMLは、ハイパーテキストを記述するための<strong>マークアップ言語</strong>です。</p>
```

<br><br><br>

---

<br><br><br>

## ```<article>``` と ```<section>```

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

