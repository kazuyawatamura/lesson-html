# 6. TIPS

# ホバーで浮き上がる演出のコード例

```html
<a href="#" class="hover">ボタン</a>
```
```css
.hover {
  display: block;
  text-align: center;
  color: #333;
  text-decoration: none;
  background-color: skyblue;
  width: 200px;
  padding: 10px;
  margin: 30px;
  border-radius: 4px;
  box-shadow: 0 2px 5px 0 rgba(0, 0, 0, .3);
  transition: all .2s ease-in-out;
  /* transform: translate(0, 0); */
  position: relative;
  top: 0;
}
.hover:hover {
  box-shadow: 0 8px 10px 0 rgba(0, 0, 0, .15);
  /* transform: translate(0, -3px);*/
  top: -3px;
}
```

参考：[ハイパフォーマンスCSS3アニメーション——60fpsを実現するベストプラクティス](https://www.webprofessional.jp/achieve-60-fps-mobile-animations-with-css3/)



# vwと%の違い
## ビューポートの単位

### vw
ビューポートの幅
### vh
ビューポートの高さ
### vmin
ビューポートの幅化高さの値が小さい方
### vmax
ビューポートの幅化高さの値が大きい方


![](https://d2mxuefqeaa7sj.cloudfront.net/s_1C4F3DB67FE10C25EFFA2013B6FF9EAD56526DFDA0962233A80C220B534DB251_1522661665145_vw.png)


※幅いっぱいにする場合、`vw`にすると横スクロールが出てしまう可能性があるので、パーセント指定をする方が良い。



# transformプロパティ

要素に対して移動（translate）、回転（rotate）、伸縮（scale）、傾斜（skew）の変形

[CSS3リファレンス transform](http://www.htmq.com/css3/transform.shtml)
[【CSS3】Transform（変形）関連のまとめ](https://qiita.com/7968/items/eddfeb4b424d7c2d2d34)


# data属性

```html
<div class="example-data" data-item="company">会社概要</div>
```
```css
.example-data {
  position: relative;
  text-align: center;
  font-size: 20px;
  width: 300px;
  margin: 0 auto;
}
.example-data::before {
  content: attr(data-item);
  position: absolute;
  top: 26px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 12px;
  text-transform: uppercase;
  font-family: Arial, sans-serif;
}
```


---
# 残り
## Grid layout
## ベンダープレフィックス
## SVG
## 縦横中央のやり方