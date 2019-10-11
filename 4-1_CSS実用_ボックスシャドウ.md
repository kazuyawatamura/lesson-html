# CSS実用、影をつけてみよう


要素に対して影をつけることができます。
昔は画像で影を表現していましたが、CSSのみで影をつけることができるようになりました。
いくつかの影の種類があるので、値のルールを覚えておきましょう。

**box-shadow.html**

```html
<div class="shadow1">ぼかしのない影を作る</div>
<div class="shadow2">左に10px、上に20px伸びる影の例</div>
<div class="shadow3">影の色を変えつつぼかす</div>
<div class="shadow4">影を拡大し、色も指定する</div>
<div class="shadow5">内側にシャドウを付ける</div>
<div class="shadow6">カンマ区切りで内側と外側両方に影をかける</div>
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

マイナス値をつける事も可能です。

```css
.shadow2 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: -20px -10px;
}
```

- 左方向に `-20px`
- 上方向に `-10px`

![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874108051_box-shadow2.png)


## 影の色を変えつつぼかす



```css
.shadow3 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 10px 11px 20px rgba(0, 0, 0, .5);
}
```

- 右方向に `10px`
- 下方向に `11px`
- ぼかし距離 `20px` ← NEW!
- 半透明の黒

3つ目の値 `20px` → ぼかし距離。値が大きいほど影がぼやけます。（負の値は指定できません）


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874124573_box-shadow3.png)


## 影を拡大し、色も指定する

```css
.shadow4 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 10px 11px 20px 12px rgba(100, 0, 0, .3);
}
```

- 右方向に `10px`
- 下方向に `11px`
- ぼかし距離 `20px`
- ぼかし距離 `12px` ← NEW!
- 半透明の黒

4つ目の値 `12px` → 広がりの距離。正の値を指定すると影の形状を「全方向」に拡大、負の値を指定すると縮小します。

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

指定すると影が内側に表示される。（内側に表示させたい時だけ書く）


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874154202_box-shadow5.png)



## カンマ区切りで内側と外側両方に影をかける

```css
.shadow6 {
  width: 200px;
  height: 100px;
  background-color: skyblue;
  box-shadow: 0px 10px 16px 0px rgba(0, 0, 0, .3),
              0px 5px 10px rgba(255,255,255,0.75) inset;
}
```

![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874163755_box-shadow6.png)


カンマ区切りで内側と外側の影を表現ができます。




![角丸にするとボタンっぽくなりますね](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1542874169864_box-shadow7.png)

角丸にするとボタンっぽくなりますね

参考：[Box Shadowのエフェクトサンプル ＆ 便利な素材まとめ](https://www.nxworld.net/tips/box-shadow-effect.html)
