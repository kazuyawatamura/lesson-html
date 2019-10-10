# レスポンシブ（responsive-html.html）

レスポンシブデザインとは、PC、タブレット、スマートフォンなどの色々なデバイスに最適化した表示を1つのHTMLファイルで対応できる方法です。


![](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1522396939826_responsive1.png)

```html
<div class="responsive">
  <div class="left">レフトコンテンツ</div>
  <div class="right">ライトコンテンツ</div>
</div>
```

[assets/css/responsive.css]

```css
.responsive {
  text-align: center;
  margin: 0 3%;
}
.responsive .left,
.responsive .right {
  padding: 20px;
}
.responsive .left {
  background-color: orange;
}
.responsive .right {
  background-color: skyblue;
}
```

## Viewport について

ブラウザでどのように見えるかを設定する為のタグです。
head内に記述します。

[Google - レスポンシブ ウェブデザインの基本](https://developers.google.com/web/fundamentals/design-and-ux/responsive/#set-the-viewport)

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```


## メディアクエリを使ってCSSを読み込む方法

### HTMLのlinkタグに記述（responsive-html.html）

```html
<link rel="stylesheet" href="assets/css/style.css" media="(min-width: 960px)">
```

### CSS内に記述（responsive-css.html）

```css
@media (max-width: 576px) { ... }
@media (min-width: 768px) and (max-width: 992px) {...}

.responsive {
  text-align: center;
  margin: 0 3%;
}
.responsive .left,
.responsive .right {
  padding: 20px;
}
.responsive .left {
  background-color: orange;
}
.responsive .right {
  background-color: skyblue;
}

@media (min-width: 768px) {
  .responsive .left {
    background-color: palegreen;
  }
  .responsive .right {
    background-color: pink;
  }        
}
```

## 書き方ルール

`min-width` → 最小の横幅が `◯◯px` の時に ~
`max-width` → 最大の横幅が `◯◯px` の時に ~

スマートフォン用のCSSから書いていくことをモバイルファースト、
デスクトップ用のCSSから書いていくことをデスクトップファーストといいます。
 

### 各デバイス用に設けたブレイクポイント

- スマートフォン　　： 576px
- タブレット　　　　： 768px
- デスクトップ　　　： 992px
- 大画面デスクトップ： 1200px

参考：[Responsive breakpoints](https://getbootstrap.com/docs/4.0/layout/overview/#responsive-breakpoints)



![クスールサイトのブレークポイントは 768px の1つです](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1522627577175_responsive2.png)




```css
.responsive {
  text-align: center;
  margin: 0 3%;
}
@media (min-width: 576px) {
  .responsive {
    display: flex;
    justify-content: center;
  }
}
.responsive .left,
.responsive .right {
  padding: 20px;
}
@media (min-width: 768px) {
  .responsive .left,
  .responsive .right {
    width: 200px;
    height: 200px;
    padding: 0;
  }
}
.responsive .left {
  background-color: orange;
}
.responsive .right {
  background-color: skyblue;
}
@media (min-width: 992px) {
  .responsive .left {
    background-color: palegreen;
  }
  .responsive .right {
    background-color: pink;
  }   
  .responsive .left,
  .responsive .right {
    width: 400px;
    height: 400px;
  }     
}
```



参考：[The Ultimate Guide To iPhone Resolutions](https://www.paintcodeapp.com/news/ultimate-guide-to-iphone-resolutions)


※デバイスが縦長か横長で振り替わる


- portrait: 縦長の場合
- landscape: 横長の場合

```css
    @media (orientation: portrait) { ... }
    @media (orientation: landscape) { ... }
```

