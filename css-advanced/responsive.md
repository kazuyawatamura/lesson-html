- [レスポンシブデザインでさまざまなデバイスに対応しよう](#レスポンシブデザインでさまざまなデバイスに対応しよう)
  - [Viewport について](#viewport-について)
  - [メディアクエリを使ってCSSを読み込む方法](#メディアクエリを使ってcssを読み込む方法)
    - [HTMLのlinkタグに記述（responsive-html.html）](#htmlのlinkタグに記述responsive-htmlhtml)
    - [CSS内に記述（responsive-css.html）](#css内に記述responsive-csshtml)
  - [書き方ルール](#書き方ルール)
    - [各デバイス用に設けたブレイクポイント](#各デバイス用に設けたブレイクポイント)


# レスポンシブデザインでさまざまなデバイスに対応しよう

レスポンシブデザインとは、PC、タブレット、スマートフォンなどの色々なデバイスに最適化した表示を1つのHTMLファイルで対応できる方法です。

<br>

![](https://laro.jp/lesson/images/lesson-css-responsive1.png)

```html
<div class="responsive">
  <div class="left">レフトコンテンツ</div>
  <div class="right">ライトコンテンツ</div>
</div>
```

<br><br>

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

<br><br><br>

## Viewport について

ブラウザでどのように見えるかを設定する為のタグです。  
head内に記述します。

[Google - レスポンシブ ウェブデザインの基本](https://developers.google.com/web/fundamentals/design-and-ux/responsive/#set-the-viewport)

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

<br><br><br>

## メディアクエリを使ってCSSを読み込む方法

<br><br><br>

### HTMLのlinkタグに記述（responsive-html.html）

```html
<link rel="stylesheet" href="assets/css/style.css" media="(min-width: 960px)">
```

<br><br><br>

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

<br><br><br>

## 書き方ルール

`min-width` → 最小の横幅が `◯◯px` の時に ~
`max-width` → 最大の横幅が `◯◯px` の時に ~

スマートフォン用のCSSから書いていくことをモバイルファースト、  
デスクトップ用のCSSから書いていくことをデスクトップファーストといいます。
 
<br><br><br>

### 各デバイス用に設けたブレイクポイント

- スマートフォン　　： 576px
- タブレット　　　　： 768px
- デスクトップ　　　： 992px
- 大画面デスクトップ： 1200px

参考：[Responsive breakpoints](https://getbootstrap.com/docs/4.0/layout/overview/#responsive-breakpoints)

<br>

![クスールサイトのブレークポイントは 768px の1つです](https://laro.jp/lesson/images/lesson-css-responsive2.png)


<br>

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

<br><br><br>

参考：[The Ultimate Guide To iPhone Resolutions](https://www.paintcodeapp.com/news/ultimate-guide-to-iphone-resolutions)

<br>
※デバイスが縦長か横長で振り替わる
<br>

- portrait: 縦長の場合
- landscape: 横長の場合

```css
    @media (orientation: portrait) { ... }
    @media (orientation: landscape) { ... }
```

