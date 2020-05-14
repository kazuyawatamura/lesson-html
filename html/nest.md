# タグの入れ子（ネスト）と要素ごとのルール

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
要素の分類（コンテンツモデル）とは「どのタグの中にどのタグを入れて良いか」を決めているルールです。  

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
→ HTMLの仕様で、pタグの中には、aタグ・imgタグ・spanタグなどの<a href="https://kazuyawatamura.github.io/lesson-html/css-basic/block-and-inline-elements.html" target="_blank">インライン要素</a>を入れることができます。  
最初から覚える必要はないのでパターンとして覚えておいてください。

```html
<!-- NG -->
<section>
  <h1>タイトル</h1>
  <li>リスト</li>
  <li>リスト</li>
  <li>リスト</li>
</section>

<!-- OK -->
<section>
  <h1>タイトル</h1>
  <ul>
    <li>リスト</li>
    <li>リスト</li>
    <li>リスト</li>
  </ul>
</section>
```
→ liタグを囲めるのは、ulタグかolタグのみです  


## 要素ごとのタグの入れ子ルール

要素ごとの入れ子ルールをよく使うタグに絞って一覧にしました。  

### divタグ：構造・レイアウト

divタグは、ほぼすべてのタグを入れ子にできます。

***a / article / aside / blockquote / br / button / div / dl / em / figure / footer / form / h1 / h2 / h3 / h4 / h5 / h6 / header / hgroup / hr / i / iframe / img / input / label / main / nav / ol / p / picture / pre / script / section / select / small / span / strong / svg / table / template / textarea / time / ul / video など***

### spanタグ：構造・レイアウト

spanタグは、同じ<a href="https://kazuyawatamura.github.io/lesson-html/css-basic/block-and-inline-elements.html" target="_blank">インライン要素</a>のタグを入れ子にできます  
（厳密には違いますがこの通り覚えておいて結構です）

***a / br / button / data / em / i / iframe / img / input / label /picture / select / small / span / strong / svg / textarea / time / video など***

### h1〜h6タグ：見出し、pタグ：段落

上記のspanと同様に<a href="https://kazuyawatamura.github.io/lesson-html/css-basic/block-and-inline-elements.html" target="_blank">インライン要素</a>のタグを入れ子にできると覚えておきましょう

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

このように1行のみの場合は迷わず間違いを発見できますが、100行〜1000行といった行数のコードで見つけるのは大変です。  
そのため、開始タグを書いたら必ず終了タグも同時に書く習慣を身に着けましょう。