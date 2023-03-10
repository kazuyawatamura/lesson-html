# CSS Grid Layout の仕組みを知ろう

Grid Layoutとは、面倒だった複雑なレイアウトを実現するための手法の1つです。<br>
Flexboxは横1方向（X軸）に強い手法だったのに対して、Grid Layoutは縦横2方向に強いレイアウト手法です。<br>
<br>
ただ覚えることが多く、複雑な設定があり初心者には難しく感じることもあります。<br>
Flexboxと比べてメリット・デメリットがありうまく使い分けていきましょう。<br>
<br><br><br>

**grid-basic.html**

```html
<ul class="container">
	<li class="item">Item1</li>
	<li class="item">Item2</li>
	<li class="item">Item3</li>
	<li class="item">Item4</li>
	<li class="item">Item5</li>
	<li class="item">Item6</li>
</ul>
```
```css
.container {
  display: grid;
  min-height: 100vh; /* ブラウザ高さいっぱいにする */
  grid-template-columns: 100px 1fr 100px;
  grid-template-rows: 80px 80px 80px;
  gap: 10px;
}
.item {
  background-color: #faa; /* 色指定 */
}
```

![](https://laro.jp/lesson/images/lesson-css-grid1.png)


- `display: grid;` : Grid Layoutを適用
- `grid-template-columns` : 列のトラックの幅を指定
- `grid-template-rows` : 行のトラックの高さを指定
- `gap` : 各アイテムの余白


<br><br><br>


## その他の名称

### ライン
アイテムを分ける行と列の線です。<br>
ラインには、左上を起点として1から順に番号が振られています。

![](https://laro.jp/lesson/images/lesson-css-grid2.png)

### セル、トラック、エリア
セルとは、行と列に配置される最小の単位です。<br>
トラックとは、コンテナの行と列の事です。<br>
エリアとは、アイテムが結合してできた集まりです。<br>
エリアには名前をつけることができて、アイテムを配置する事ができます。

![](https://laro.jp/lesson/images/lesson-css-grid3.png)

<br><br><br>


## `1fr` とは？

frとは、「fraction(比率)」のことでコンテナーに応じたアイテムのサイズを割合で指定する事ができます。<br>
<br>
下記の図を表すと `grid-template-columns: 100px 1fr 1fr 2fr;` となります。<br>
frの合計から、それぞれの数値が割合となって割り当てられます。<br>
ざっくりと**固定幅以外のスペースをどのくらいの割合で埋めるか**、と覚えてください。

![](https://laro.jp/lesson/images/lesson-css-grid4.png)

<br><br><br>

## `gap` とは？

アイテム間の余白を指定できます。<br>
Flexboxでもgapプロパティを用いて余白の調整が可能です。

- `gap`　-　縦方向と横方向のアイテム間の余白
- `row-gap`　-　縦方向のアイテム間の余白
- `column-gap`　-　横方向のアイテム間の余白

```css
.container {
  display: grid;
  row-gap: 20px;
  column-gap: 30px;

  /* ショートハンド */
  gap: 20px; /* 縦横20pxの場合 */
  gap: 20px 30px; /* 縦20px 横30pxの場合 */
}
```

<br><br><br>


## エリアに名前をつけて指定する

それぞれのエリアに名前をつけてレイアウトをしていきます。<br>
`.container` でレイアウトを明示的に決めて、それぞれのアイテムで名前を同期します。

完成形はこちらです。

![](https://laro.jp/lesson/images/lesson-css-grid5.png)

まずHTMLを記述します。

```html
<div class="container">
  <header class="header">header</header>
  <main class="main">main</main>
  <aside class="aside">aside</aside>
  <nav class="nav">nav</nav>
  <footer class="footer">footer</footer>
</div>
```

<br>

### 1. `grid-template-areas`でエリアに名前をつける

```css
.container {
  display: grid;
  min-height: 100vh; /* ブラウザ高さいっぱいにする */
  gap: 10px 30px;
  grid-template-columns: 180px 1fr 80px;
  grid-template-rows: 60px 1fr 90px;
	
  grid-template-areas:
    "header header header"
    "aside  main   nav   "
    "footer footer footer";
}
/* エリアに名前をつける */  
.header {
  grid-area: header;
  background-color: #F24E1E;
}
.nav {
  grid-area: nav;
  background-color: #1ABCFE;
}
.main {
  grid-area: main;
  background-color: #FF7262;
}
.aside {
  grid-area: aside;
  background-color: #A259FF;
}
.footer {
  grid-area: footer;
  background-color: #0ACF83;
}
```
<br>

### 2. `grid-template`でエリア名と各サイズを明示的に配置する
```css
.container {
  display: grid;
  min-height: 100vh; /* ブラウザ高さいっぱいにする */
  gap: 10px 30px;
	grid-template:
    "header header header" 60px
    "aside  main   nav   " 1fr
    "footer footer footer" 90px
    / 180px   1fr   80px;
}
/* エリアに名前をつける */  
.header {
  grid-area: header;
  background-color: #F24E1E;
}
.nav {
  grid-area: nav;
  background-color: #1ABCFE;
}
.main {
  grid-area: main;
  background-color: #FF7262;
}
.aside {
  grid-area: aside;
  background-color: #A259FF;
}
.footer {
  grid-area: footer;
  background-color: #0ACF83;
}
```





<br><br><br>

## grid-template-columns

列の数とサイズを設定する為のプロパティです。


| grid-template-columns | 列の数と幅を定義                                     |
| -------------- | ---------------------------------------------------------------- |
| 100px 1fr 60px  | ![image.png](https://laro.jp/lesson/images/lesson-css-grid-properties1.png) |
| 1fr 1fr 1fr  | ![image.png](https://laro.jp/lesson/images/lesson-css-grid-properties2.png) |

<br><br><br>

## grid-template-rows

行の数とサイズを設定する為のプロパティです。


| grid-template-rows | 行の数と幅を定義                                     |
| -------------- | ---------------------------------------------------------------- |
| 200px 1fr 100px  | ![image.png](https://laro.jp/lesson/images/lesson-css-grid-properties3.png) |
| 1fr 1fr 1fr  | ![image.png](https://laro.jp/lesson/images/lesson-css-grid-properties4.png) |

<br><br><br>


## 1次元方法に対する便利なコード例

![image.png](https://laro.jp/lesson/images/lesson-css-grid-repeat1.png)

```css
grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
```

- `repeat` アイテム数の変動に対応
- `auto-fill` または `auto-fit` 親要素が可変幅でもアイテムのサイズを調整、またはカラム落ちさせる
- `minmax(200px, 1fr)`アイテムの最小サイズ200px、最大サイズ1fr

<br><br>

### repeat関数

同じサイズが続く時にrepeat関数で部分的な繰り返しができます。<br>
この関数は CSS グリッドのプロパティである `grid-template-columns` と `grid-template-rows` の中で使う事が可能です。

```css
grid-template-columns: repeat(3, 1fr);
/*
繰り返す回数, サイズ 
1fr 1fr 1fr と同じ意味
*/
```

#### 第一引数（繰り返す回数）
* 整数
* auto-fit
  - 親要素にスペースが余る場合、空のグリッドが生まれる
* auto-fill
  - 親要素にスペースが余る場合、余白として扱われる

:::note info
auto-fitとauto-fillは後述するminmax()関数と合わせて使うと効果的です。
:::


#### 第二引数（サイズ）
* 整数
* fr
* minmax()

スペースを空けて複数のサイズを指定することも可能。

### minmax()

2つの引数を取る、最小値と最大値が設定できる関数です。
* 整数
* fr
* auto


```html
<div class="container">
  <div>サイズ：50px.</div>
  <div>サイズ：1fr.</div>
  <div>サイズ：50px.</div>
  <div>サイズ：1fr.</div>
  <div>サイズ：100px.</div>
</div>
<div class="container minmax">
  <div>Item</div>
  <div>Item</div>
  <div>Item</div>
  <div>Item</div>
  <div>Item</div>
  <div>Item</div>
</div>
```

```css
.container {
  display: grid;
  grid-template-columns: repeat(2, 50px 1fr) 100px;
  gap: 10px;
  /* 以下スタイリング用 */
  box-sizing: border-box;
  height: 200px;
  width: 100%;
  background-color: #eee;
  padding: 10px;
}
.container > div {
  background-color: #faa;
}
.container.minmax {
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
}
```

↓ `grid-template-columns: repeat(2, 50px 1fr) 100px;` の場合
![image.png](https://laro.jp/lesson/images/lesson-css-grid-repeat2.png)

↓ `grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));` の場合
![image.png](https://laro.jp/lesson/images/lesson-css-grid-repeat3.png)




#### 参考文献
> https://developer.mozilla.org/ja/docs/Web/CSS/repeat<br>
> https://shu-naka-blog.com/css/repeat/#repeat<br>
> https://shu-naka-blog.com/css/auto-fit-fill/