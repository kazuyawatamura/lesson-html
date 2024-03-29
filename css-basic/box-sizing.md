- [box-sizingプロパティについて](#box-sizingプロパティについて)
    - [書き方の例](#書き方の例)
  - [content-boxの場合](#content-boxの場合)
    - [300pxのボックスを作りたい場合](#300pxのボックスを作りたい場合)
  - [border-box の場合](#border-box-の場合)
  - [width:100%とautoの違いは？](#width100とautoの違いは)


# box-sizingプロパティについて

要素の幅（width）や高さ（height）の中にpaddingとborderを含めるかどうかというプロパティです。

```css
/* paddingとborderを幅と高さに含めない */
box-sizing: content-box; /* 初期値 */

/* paddingとborderを幅と高さに含める */
box-sizing: border-box;
```

### 書き方の例
```html
<p class="box-sizing">要素の幅や高さに含めるかどうか。</p>
```
```css
.box-sizing {
  box-sizing: border-box;
  width: 300px;
  padding: 20px;
  border: 1px solid orange;
}
```
<br><br><br>

## content-boxの場合

paddingとborderを幅（width）と高さ（height)に含めない。  
幅（width）と高さ（height）に足されるため、レイアウトがしづらい。

### 300pxのボックスを作りたい場合

254px = 300px - ( 26px x 2 ) + ( 3px x 2 )  
※ 2というのは両端辺の数です。

```css
.content-box {
  width: 254px;
  padding: 26px;
  border: 3px solid #CCC;
}
```


![](https://laro.jp/lesson/images/lesson-css-boxsizing1.png)


<br><br><br>

## border-box の場合

上記の `content-box` のデメリットを解決できるのが、`box-sizing: border-box;` です。  
paddingとborderを幅（width）と高さ（height）に含めることができます。


![](https://laro.jp/lesson/images/lesson-css-boxsizing2.png)


content-boxの場合、width + padding + border を足した幅を計算しなければならず使いづらいので理由がない限り、border-boxを指定します。

下記をオマジナイのように書くと、pタグやクラスに1つひとつ要素に指定せず、記述するHTMLすべての要素が `border-box` になります。

```css
html {
  box-sizing: border-box;
}
*, *::before, *::after {
  box-sizing: inherit;
}
```

別資料でお伝えするリセットCSSにすでに記述されておりますので、リセットCSSを読み込むだけで `border-box` になります。


<br><br><br>

## width:100%とautoの違いは？

![](https://laro.jp/lesson/images/lesson-css-boxsizing3.png)

- auto：widthの中にpaddingとborderが含まれる。
- 100%：widthにはpaddingとborderの分が含まれません。

上記の `box-sizing: border-box;` をすればとくに意識する必要はありません。  
※ ただしmarginは除きます。

