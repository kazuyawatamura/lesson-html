# Floatで回り込み

<br><br><br>

## floatプロパティとは？

**float-basic.html**

昔から使われている横並び用のCSS。  
レイアウト調整用のCSSと言えばfloatだったが、本来の用途は、特定の要素を左右に寄せて配置するプロパティ。  
たとえば、文章中の画像に回り込ませる為のCSSでした。  


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-float1.png)


```html
<p class="float-text">
  吾輩は猫である。名前はまだ無い。どこで生れたかとんと見当がつかぬ。
  <img src="https://picsum.photos/140/70" alt="" class="float-image">
  何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪な種族であったそうだ。この書生というのは時々我々を捕えて煮て食うという話である。しかしその当時は何という考もなかったから別段恐しいとも思わなかった。ただ彼の掌に載せられてス
</p>
```
```css
.float-text {
  width: 400px;
}
.float-image {
  float: right;
  padding: 16px;
  margin: 8px;
  background-color: #eee;
}
```

回り込みしたい要素（上記は `<img>` タグ）に対して

- float: left;と指定すれば、画像は左側に寄り、
- float: right;と指定すれば、画像は右側に寄る。
- 初期値は、 `none` 

<br><br><br>

## floatで横並び1

**float-clear.html**

```html
<div class="orange">オレンジ</div>
<div class="skyblue">ブルー</div>
<div class="red">レッド</div>
```
```css
.orange {
  background-color: orange;
  width: 200px;
  height: 250px;
  float: left;
}
.skyblue {
  background-color: skyblue;
  width: 150px;
  height: 100px;
  float: left;
}
.red {
  background-color: red;
  width: 500px;
  height: 80px;
  float: left;
}
```

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-float2.png)

<br><br><br>

### 注意点

`.red`  要素から  `float: left;`  を削除してみると。。。


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-float3.png)



-  `.red`  要素は  `float: left`  を削除したにもかからわらず、横並びのまま
- 横幅が短くなっている

floatプロパティを適応した要素は、「浮いてしまう」ような状態になってしまいます。




![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-float4.png)

<br><br><br>

### 解決策

```css
.red {
  background-color: red;
  width: 500px;
  height: 80px;
  clear: left; /* <- または、right , both */
}
```

<br><br><br>

## floatで横並び2

**float-overflow.html**

```html
<div class="wrap">
  <div class="orange">オレンジ</div>
  <div class="skyblue">ブルー</div>
  <div class="red">レッド</div>
</div>
```
```css
.wrap {
  background-color: palegreen;
}
.orange {
  background-color: orange;
  width: 200px;
  height: 250px;
  float: left;
}
.skyblue {
  background-color: skyblue;
  width: 150px;
  height: 100px;
  float: left;
}
.red {
  background-color: red;
  width: 500px;
  height: 80px;
  float: left;
}
```


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-float5.png)

<br><br><br>

### 解決策1（推奨）
```css
.wrap {
  overflow: hidden; /* <- 追加 */
  background-color: palegreen;
}
```
<br><br><br>

### 解決策2
縦サイズが決まっていればこの方法のほうが手っ取り早いと思いますが、レスポンシブサイトを作るのであれば面倒な手法かもしれません。

```css
.wrap {
  height 300px;　/* <- 高さを指定する */
  background-color: palegreen;
}
```
<br><br><br>

### 解決策3

htmlの方に `clearfix` というクラスを追加します。

```html
<div class="wrap clearfix">
```

そのクラスに以下のようなプロパティを設定します。

```css
.clearfix::after{
  content: "";
  display: block;
  clear: both;
}
```

クリアーフィックスという手法の解決方法です。  
IEが古い時代に回避方法としてベターだったこの方法ですが、時代と共に使われなくなってきました。  
古いサイトのリニューアル案件などでもしかしたら利用されているかもしれません。  