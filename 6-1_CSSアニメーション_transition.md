# 6_CSSアニメーション_transition


プロパティに変更があった時に、一定時間でプロパティを変化させる設定。
マウスオーバーなど単純な動きのアニメーションを実装する時に利用します。



![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522288460873_Kapture+2018-03-29+at+10.53.47.gif)


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


## transition-property

どのプロパティにアニメーションを適用するか指定するプロパティ。

初期値は、 ```**all**` 

 `all`  を指定すると、全てのプロパティにアニメーションを適用する。
下の要素は  `background-color`  を指定しているため、それ以外のプロパティを変更しても
アニメーションが適用されません。

### all

![全てのプロパティに対してアニメーションが適用](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291006012_Kapture+2018-03-29+at+11.36.31.gif)


### background-color

![背景色のみアニメーションが適用](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291199753_Kapture+2018-03-29+at+11.39.54.gif)




## transition-duration

アニメーションが始まってから終わるまでの時間を指定します。
単位を秒数  `s` （またはミリ秒 `ms` ）で指定します。 `margin: 0;` のように単位は省略できません。必ず  `s` などをつけてください。

初期値は  `0s` 

例 
 `transition-duration: .5s;`   → 0.5秒

### 3秒


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291610651_Kapture+2018-03-29+at+11.46.18.gif)


### 0.5秒

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291665197_Kapture+2018-03-29+at+11.47.38.gif)



## transition-delay

アニメーションが開始するまでの遅延時間を指定するプロパティ。

初期値は、 `0` 


### 1秒

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291806943_Kapture+2018-03-29+at+11.49.44.gif)


### 0秒

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291862165_Kapture+2018-03-29+at+11.50.53.gif)




## transition-timing-function

アニメーションのイージングを指定するプロパティ。

初期値は、  `ease` 


![via: https://developers.google.com/web/fundamentals/design-and-ux/animations/the-basics-of-easing?hl=ja](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522299879568_transition-timing-function.png)


### linear
一定

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300294765_linear.gif)


### ease-out
ゆっくり終わる

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300250520_ease-out.gif)


### ease-in
ゆっくり始まる

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300364242_ease-in.gif)


### ease-in-out
ゆっくり始まってゆっくり終わる

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300444293_ease-in-out.gif)


### cubic-bezier()
3次ベジェ曲線のP1とP2を (x1, y1, x2, y2) で指定


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300654127_Kapture+2018-03-29+at+14.17.24.gif)


http://cubic-bezier.com/


### ショートハンド

```css
transition : all .5s 0s ease-out;
```

※遅延処理（delay）はあまり使わないので省略する事が多い。




参考：[CSSのみで実装するボタンデザインやホバーエフェクト 20＋α](https://www.nxworld.net/tips/css-only-button-design-and-hover-effects.html)


