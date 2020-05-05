# 座標で自由にレイアウトしよう（Position）

<br><br><br>

## positionプロパティとは？

**position-basic.html**

Positionは、要素の位置を座標で決めるためのプロパティです。  
座標でパーツを配置できるので自由度が上がります。その反面、デバイスの幅が変化したさいに画面外へ、はみ出してしまったりコントロールがしにくいデメリットもあります。  


全体的なレイアウトはFlexboxで行い、部分的なパーツのレイアウトはPositionで行うと良いかと思います。


```html
<img src="https://picsum.photos/300/300/" alt="ポジション" class="image">
```
```css
.image {
  position: absolute;
  top: 300px;
  left: 20px;
}
```
<br>

### positionプロパティ

基準の位置の指定

- static　　← 初期値
- absolute  ← 親要素を基準に絶対的な位置を決める（上記はbodyが親要素）
- relative　← 現在の位置を基準に相対的な位置を決める
- fixed　　← 画面上の指定した位置に固定する


#### 基準からの距離

- top　　　← 上からの距離
- bottom　←下からの距離
- left　　　←左からの距離
- right　　 ←右からの距離


#### 実際の使い方（1）

```html
<div class="relative">
  <div class="absolute">要素</div>
</div>
```
```css
.relative {
  position: relative;
  width: 500px;
  height: 300px;
  background-color: #eee;
}
.absolute {
  position: absolute;
  top: 100px;
  left: 200px;
  background-color: red;
}
```

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-position1.png)

<br>

#### 実際の使い方（position-photo.html）

```html
<div class="relative">
  <div class="absolute">This photo.</div>
</div>
```
```css
.relative {
  position: relative;
  width: 500px;
  height: 300px;
  background: url(https://picsum.photos/500/300/)
}
.absolute {
  position: absolute;
  bottom: 20px;
  right: 20px;
  color: #ffffff;
  font-size: 22px;
  font-family: sans-serif;
  padding: 8px;
  background-color: red;
}
```
<br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-position2.png)

<br>

- マイナス数値も可能。 `right: -20px;`  
- 50% と マイナスマージンで中央に配置する事も可能


#### 注意

* `absolute`  を使って位置調整するときは、親要素に  `position: relative`  を指定しておきましょう。  
基準位置がずれて定まらず、思った位置になりません。
* `absolute`  を使うときは、おまじないのように親要素もセットで変えるようにしましょう。


<br><br><br>

## 固定位置

**position-fixed.html**  

画面の決まった位置に固定表示をさせるプロパティです。  
下記のサイトのように下にスクロールしてもヘッダーやナビゲーションがついてくるようにできます。  


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-position3.gif)


```html
<p>これは文章です1</p>
<p>これは文章です2</p>
<p>これは文章です3</p>
<p>これは文章です4</p>
<p>これは文章です5</p>
<p>これは文章です6</p>
<p>これは文章です7</p>
<p>これは文章です8</p>
<p>これは文章です9</p>
<p>これは文章です10</p>
<p>これは文章です11</p>
<p>これは文章です12</p>
<p>これは文章です13</p>
<p>これは文章です14</p>
<p>これは文章です15</p>
<p>これは文章です16</p>
<p>これは文章です17</p>
<p>これは文章です18</p>
<p>これは文章です19</p>
<p>これは文章です20</p>
<div class="fixed">固定領域</div>
```
```css
p {
  margin-top: 30px;
}
.fixed {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: orange;
}
```

※位置の基準は親要素ではなく「ウィンドウ全体」  
よくみるページトップ戻るボタンにも有効です

```html
<div class="fixed">ページトップ</div>
```
```css    
.fixed {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
.fixed a {
  display: block;
  text-align: center;
  text-decoration: none;
  color: #fff;
  width: 100px;
  padding: 8px;
  background-color: orange;
}
```