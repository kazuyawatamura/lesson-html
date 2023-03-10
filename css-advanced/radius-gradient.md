- [角丸とグラデーションで表現の幅を広げよう](#角丸とグラデーションで表現の幅を広げよう)
  - [角丸](#角丸)
    - [ショートハンド](#ショートハンド)
  - [](#)
  - [グラデーション（gradient.html）](#グラデーションgradienthtml)
    - [グラデーションの方向を設定する](#グラデーションの方向を設定する)


# 角丸とグラデーションで表現の幅を広げよう

<br><br><br>

## 角丸

**border-radius.html**

CSSで要素に対して四方に角丸を設定できるプロパティです。


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-radius1.png)


四隅に同じ値の角丸を設定したい場合、以下のように記述します。  
半径20pxの正円の円弧をベースにした角丸を実装ができます。


```html
<div class="radius">角丸</div>
```
```css
.radius {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  border-radius: 20px;
}
```

四隅に異なる値を設定したい場合は以下のように記述します。

<br>

![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-radius2.png)

<br>

```css
.radius {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  border-top-left-radius: 10px;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 30px;
  border-bottom-left-radius: 40px;
}
```

<br><br><br>

### ショートハンド

左上、右上、左下、右下の順に記述（左上を基準に時計回り）

```css
border-radius: 10px 20px 30px 40px;
```
<br><br><br>
---
<br><br><br>

## グラデーション（gradient.html）

CSSでグラデーションを設定ができます。  
デザインのアクセントや要所で使うことがあるので、ぜひ覚えておきましょう。


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-radius3.png)


```html
<div class="gradient">グラデーション</div>
```
```css
.gradient1 {
  text-align: center;
  width: 200px;
  height: 100px;
  line-height: 100px;      
  background: linear-gradient(#FAD961, #F76B1C);
}
```
<br><br><br>

### グラデーションの方向を設定する


![](https://laro.jp/wp-content/uploads/2019/11/lesson-css-radius4.png)


```css
    .gradient1 {
      text-align: center;
      width: 200px;
      height: 100px;
      line-height: 100px;      
      background: linear-gradient(90deg, #FAD961, #F76B1C);
    }
```

<br>

> deg = degree（デグリー）

<br>

**90deg** ではなく、 `to bottom`   `to left`    `to bottom right`  でも設定ができます。

<br><br><br>

CSS Gradient Generator  
https://cssgradient.io/

Gradient Gallery  
https://webgradients.com/

