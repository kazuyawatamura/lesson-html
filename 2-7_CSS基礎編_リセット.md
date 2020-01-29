# リセットcssについて

HTMLタグには、すでにブラウザ毎にスタイルがあらかじめ割り当てられている場合があります。  
たとえば、`<ul>` タグには左にpadding、上下にmarginがあらかじめ入っています。

オレンジ色の部分が `margin-top` と `margin-bottom`、グリーン色が `padding-left` がデフォルトで設定されています。

![](https://paper-attachments.dropbox.com/s_C912F9347878F8C42187583094181784B83B4BA609FE32A97CC1B9CA603258CA_1570774769531_+2019-10-11+15.19.13.png)


タグ毎によってそれぞれのスタイルがついており、かつスタイルがブラウザごとに違います。  
（Google Chromeでは10px、他のブラウザでは8pxなど）

リセットCSSとは、そのブラウザごとのスタイルを一度 **リセット** してCSSでのコーディングをスムーズに行うために開発されたCSSです。

<br><br><br>

## 具体的にはどのようにリセットCSSを用意すれば良いのか

主にインターネット上に昔から使われてきたリセットCSSや海外の開発者が作ったもの、そして自作するリセットCSSのいずれかを利用することになります。

下記に人気の高いリセットCSSを上げていきます。


- [Eric Meyer’s “Reset CSS” 2.0](https://meyerweb.com/eric/tools/css/reset/)
    - もっとも使われているリセットCSS（2008年）
- [html-5-reset-stylesheet](http://html5doctor.com/html-5-reset-stylesheet/)
    - Eric Meyer’s CSS reset を HTML5 で使うために修正したもの（2009年）
- [Normalize css](https://necolas.github.io/normalize.css/)
    - デフォルトのスタイルはあえて残しつつ、ブラウザごとの違いを修正するという考え方で作られている。（開発継続中）
- [ress](https://coliss.com/articles/build-websites/operation/css/modern-css-reset-ress.html)
    - 上記の `Normalize.css` をカスタマイズしたリセットCSS（開発継続中）

<br><br><br>

### 自作CSS

使いまわししやすいように `ress` リセットCSSをカスタマイズしたファイルを下記にアップしているので、こちらを利用してください。

[https://github.com/kazuyawatamura/reset-css](https://github.com/kazuyawatamura/reset-css)

box-sizingの資料にあった下記のコードもこのリセットCSSに記述されています。

```css
html {
  box-sizing: border-box;
}
*, *::before, *::after {
  box-sizing: inherit;
}
```
