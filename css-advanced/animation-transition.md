# 6_CSSアニメーション_transition


プロパティに変更があった時に、一定時間でプロパティを変化させる設定。  
マウスオーバーなど単純な動きのアニメーションを実装する時に利用します。

<br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition1.gif)

<br><br><br>

## まずファイルを用意します（transition.html）

```html
<div class="animation">アニメーション</div>
```
```css
.animation {
  width: 150px;
  height: 100px;
  background: orange;
  transition-property: all;
  transition-duration: .5s;
  transition-delay: 0s;
  transition-timing-function: ease;
}
.animation:hover {
  width: 300px;
  background: skyblue;
}
```

<br><br><br>

## transition-property

どのプロパティにアニメーションを適用するか指定するプロパティ。

初期値は、 ```**all**` 

 `all`  を指定すると、全てのプロパティにアニメーションを適用する。
下の要素は  `background-color`  を指定しているため、それ以外のプロパティを変更しても
アニメーションが適用されません。


### all

![全てのプロパティに対してアニメーションが適用](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition2.gif)


### background-color

![背景色のみアニメーションが適用](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition3.gif)

<br><br><br>

## transition-duration

アニメーションが始まってから終わるまでの時間を指定します。
単位を秒数  `s` （またはミリ秒 `ms` ）で指定します。 `margin: 0;` のように単位は省略できません。必ず  `s` などをつけてください。

初期値は  `0s` 

例 
 `transition-duration: .5s;`   → 0.5秒

### 3秒

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition4.gif)

### 0.5秒

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition5.gif)

<br><br><br>

## transition-delay

アニメーションが開始するまでの遅延時間を指定するプロパティ。

初期値は、 `0` 

### 1秒

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition6.gif)

### 0秒

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition7.gif)

<br><br><br>

## transition-timing-function

アニメーションのイージングを指定するプロパティ。

初期値は、  `ease` 


![via: https://developers.google.com/web/fundamentals/design-and-ux/animations/the-basics-of-easing?hl=ja](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition8.png)
via: https://developers.google.com/web/fundamentals/design-and-ux/animations/the-basics-of-easing?hl=ja


### linear
一定

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition9.gif)


### ease-out
ゆっくり終わる

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition10.gif)


### ease-in
ゆっくり始まる

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition11.gif)


### ease-in-out
ゆっくり始まってゆっくり終わる

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition12.gif)


### cubic-bezier()
3次ベジェ曲線のP1とP2を (x1, y1, x2, y2) で指定


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-transition13.gif)


http://cubic-bezier.com/


### ショートハンド

```css
transition : all .5s 0s ease-out;
```

※遅延処理（delay）はあまり使わないので省略する事が多い。




参考：[CSSのみで実装するボタンデザインやホバーエフェクト 20＋α](https://www.nxworld.net/tips/css-only-button-design-and-hover-effects.html)


