# 最小最大幅でさまざまなデバイスに対応

レスポンシブデザインでサイトを制作する際によく用いるプロパティです。  
ブロック要素の最小幅と最大幅を設定ができます。

**相対値（%）で指定した `width`** と併用する事によってブラウザの幅に応じて可変するレイアウトを作ってみましょう。

**min-max.html**

<br><br><br>

## 最小幅（min-width）について

要素がこれ以上小さくならない幅を指定し `width` の最小値として設定します。  
小さいデバイスやブラウザの幅を狭めたときに小さくなりすぎないように `min-width` を設定します。

```html
<div class="min-width">
  <p class="nomin">最小幅なし</p>
  <p class="min">最小幅100px</p>
</div>
```

```css
.min-width {
  width: 90%;/*親要素大きめ*/
  background: skyblue;
}
.min-width .nomin {/*最小幅なし*/
  background: white;
  width: 50%
}
.min-width .min {/*最小幅あり*/
  background: orange;
  width: 50%;
  min-width: 100px
}
```

下記の動画のオレンジ色の要素の最小幅を設定しています。  
**親要素の50%を保たれつつ、縮小されていますが100pxでストップして、それ以上は縮みません。**

<br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-minmax1.gif)

<br><br><br>

## 最大幅（max-width）について

`min-width` の逆の考え方で、要素がこれ以上大きくならない幅を指定し `width` の最大値として設定します。  
PCや大きなタブレットなど大きなデバイスやブラウザの幅を広めたときに大きくなりすぎないように `max-width` を設定します。

```html
<div class="max-width">
  <p class="nomin">最大幅なし</p>
  <p class="min">最大幅100px</p>
</div>
```
```css
.max-width {
  width: 90%;/*親要素小さめ*/
  background:skyblue;
}
.max-width .nomin {/*最大幅なし*/
  background: white;
  width: 80%
}
.max-width .min {/*最大幅あり*/
  background:orange;
  width: 80%;
  max-width: 500px
}
```

下記の動画のオレンジ色の要素の最大幅を設定しています。  
**親要素の50%を保たれつつ、拡大されていますが500pxでストップして、それ以上は広がりません。**

<br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-minmax2.gif)

<br><br><br>

### 最大幅（max-width）の実例

大きい画像をスマホで見たときに画像が画面からはみ出さないように制限してみましょう。  
大きさ縦横500pxの画像に対して `max-width: 100%;` を設定します。  
そうして500px以下のブラウザサイズで見たときに、画面からはみ出さずに収まりました。


```html
<div class="max-width-img">
  <img src="https://picsum.photos/500/500?randam" alt="">
</div>
```

```css
.max-width-img {
  text-align: center;
}
.max-width-img img {
  width: 500px;
  height: 500px;
  max-width: 100%;
}
```

<br>

![](https://laro.jp/wp-content/uploads/2020/01/lesson-css-minmax3-github.gif)

<br>

しかし、`500px` 以下になって幅だけ `max-width` により小さくなったせいで、画像の縦横比が変化してしまいました。  
そこで**画像の縦横比を保つ方法**をご紹介します。  

それは、`height` を `auto` にすることです。  
縦を `auto` にすることによって縦が可変になり、横幅に応じて変化するようになりました。

```css
.max-width-img {
  text-align: center;
}
.max-width-img img {
  width: 500px;
  height: auto; /* ←ここをautoに変更 */
  max-width: 100%;
}
```
<br>

![](https://laro.jp/wp-content/uploads/2020/01/lesson-css-minmax4-github.gif)