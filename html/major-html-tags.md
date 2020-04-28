# タグの入れ子（ネスト）

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

<br><br><br>

## 要素の分類（コンテンツモデル）
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


## 要素ごとのタグの入れ子ルール

要素ごとの入れ子ルールをよく使うタグに絞って一覧にしました。  

### divタグ：構造・レイアウト

divタグは、ほぼすべてのタグを入れ子にできます。

***a / article / aside / blockquote / br / button / div / dl / em / figure / footer / form / h1 / h2 / h3 / h4 / h5 / h6 / header / hgroup / hr / i / iframe / img / input / label / main / nav / ol / p / picture / pre / script / section / select / small / span / strong / svg / table / template / textarea / time / ul / video など***

### spanタグ：構造・レイアウト

spanタグは、同じインライン要素のタグを入れ子にできます（厳密には違いますが左記の通り覚えておいて結構です）

***a / br / button / data / em / i / iframe / img / input / label /picture / select / small / span / strong / svg / textarea / time / video など***

### h1〜h6タグ：見出し、pタグ：段落

上記のspanと同様に同じインライン要素のタグを入れ子にできると覚えておきましょう

***a / br / button / data / em / i / iframe / img / input / label /picture / select / small / span / strong / svg / textarea / time / video など***

### ul / olタグ：リスト定義

ulもolタグのどちらも基本的には、入れ子できるのはliタグのみです。

***li***

### liタグ：リスト定義（子要素）

divのように多くのタグを入れ子にできる万能なタグです。  
上記の「リストの入れ子」のように階層構造にもできます。

***a / article / aside / blockquote / br / button / div / dl / em / figure / footer / form / h1 / h2 / h3 / h4 / h5 / h6 / header / hgroup / hr / i / iframe / img / input / label / main / nav / ol / p / picture / pre / script / section / select / small / span / strong / svg / table / template / textarea / time / ul / video***

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


<br><br><br>

## 開始タグと閉じタグの位置を合わせましょう

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

正解はこちらです！  
答え：strongタグとpタグの終了タグの位置が変わっています。

```html
<p>HTMLは、ハイパーテキストを記述するための<strong>マークアップ言語</strong>です。</p>
```



## HTML5タグを用いたセクショニング

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

