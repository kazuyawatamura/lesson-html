
# CSS実用、角丸とグラデーション



## 角丸

**border-radius.html**

CSSで要素に対して四方に角丸を設定できるプロパティです。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522306298448_border-radius1.png)


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


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522306688289_border-radius2.png)



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

### ショートハンド

左上、右上、左下、右下の順に記述（左上を基準に時計回り）

```css
border-radius: 10px 20px 30px 40px;
```

---

## グラデーション（gradient.html）

CSSでグラデーションを設定ができます。
デザインのアクセントや要所で使うことがあるので、ぜひ覚えておきましょう。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522310087899_gradient1.png)


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



### グラデーションの方向を設定する


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522310655503_gradient2.png)


```css
    .gradient1 {
      text-align: center;
      width: 200px;
      height: 100px;
      line-height: 100px;      
      background: linear-gradient(90deg, #FAD961, #F76B1C);
    }
```

> deg = degree（デグリー）

**90deg** ではなく、 `to bottom`   `to left`    `to bottom right`  でも設定ができます。



CSS Gradient Generator
https://cssgradient.io/

Gradient Gallery
https://webgradients.com/

