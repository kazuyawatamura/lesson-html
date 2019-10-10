# シャドウ（box-shadow.html）


要素に対して影をつけることができます。


```html
<div class="shadow1">シャドウ</div>
```


## ぼかしのない影を作る

```css
.shadow1 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 10px 10px;
}
```

- ひとつ目の `10px` が左右の値
- ふたつ目の `10px` が上下の値
![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874095278_box-shadow1.png)


### 左に10px、上に20px伸びる影の例

```css
.shadow2 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: -20px -10px;
}
```


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874108051_box-shadow2.png)


## 影の色を変えつつぼかす

```css
.shadow3 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 10px 10px 20px gray;
}
```

![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874124573_box-shadow3.png)


## 影を拡大し、色も指定する

```css
.shadow4 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 10px 10px 20px 10px rgba(100, 0, 0, .3);
}
```

![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874144913_box-shadow4.png)


## 内側にシャドウを付ける

```css
.shadow5 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 10px 10px 20px 0 rgba(0, 0, 0, .5) inset;
}
```

![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874154202_box-shadow5.png)



## カンマ区切りで内側と外側両方に影をかける

```css
.shadow6 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 0px 10px 16px 0px rgba(0, 0, 0, .3), 0px 5px 10px rgba(255,255,255,0.75) inset;
}
```

![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874163755_box-shadow6.png)

![角丸にするとボタンっぽくなりますね](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874169864_box-shadow7.png)



参考：[Box Shadowのエフェクトサンプル ＆ 便利な素材まとめ](https://www.nxworld.net/tips/box-shadow-effect.html)
