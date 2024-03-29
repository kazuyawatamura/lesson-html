- [CSS（スタイルーシート）とは](#cssスタイルーシートとは)
  - [CSSの基本的な書き方](#cssの基本的な書き方)
    - [POINT](#point)
  - [記述する場所について](#記述する場所について)
    - [1.HTMLタグに直接記述する](#1htmlタグに直接記述する)
    - [2.head要素内に記述する](#2head要素内に記述する)
    - [3. 外部ファイルに記述する](#3-外部ファイルに記述する)
  - [CSSのコメントの書き方](#cssのコメントの書き方)


# CSS（スタイルーシート）とは

**Cascading Style Sheetsの略**
HTMLが文章構造を指定する言語であるのに対して、  
CSSはそのHTML文章のレイアウトや装飾などの見た目を指定する為の言語です。

<br><br>

![](https://laro.jp/lesson/images/lesson-html-cssbasic1.png)

<br><br>

![](https://laro.jp/lesson/images/lesson-html-cssbasic2.png)

<br><br><br>

---
## CSSの基本的な書き方


![](https://laro.jp/lesson/images/lesson-html-cssbasic3.png)



- セレクター　：　適用する対象　　　　　← どれ
- プロパティ：　スタイルの種類　　　　← 何を
- 値　　　　：　適用させたい結果　　　← どうするか

<br><br><br>

### POINT

- プロパティと値は波括弧で囲う
- プロパティと値はコロン（：）でつないでセミコロン（；）で終わる


```css
p {
  color: red;
  font-weight: bold;
  margin-left: 20px;
}
```
↓
```css
pタグの {
  色を: 赤にする;
  太さを: 太くする;
  左側の隙間を: 20pxにする;
}
```

<br><br><br>

---

<br><br><br>

## 記述する場所について

<br><br><br>

### 1.HTMLタグに直接記述する

HTMLタグの中に半角スペースで直接CSSを書くことができます。  
そのタグのみに該当のCSSを充てることができます。

```html
<p style="color: red;">この文字を赤にしたい。</p>
```

<br><br><br>

### 2.head要素内に記述する

HTMLタグのheadタグの中にCSSを書くことができます。  
そのページ上にあるセレクターのみにCSSを充てることができます。

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>セレクタの練習1</title>
    <style>
      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <p>この文字を赤にしたい。</p>
  </body>
</html>
```

<br><br><br>

### 3. 外部ファイルに記述する

もっともポピュラーな書き方。  
`<link>` を使ってCSSを外部ファイル化することで管理がしやすく、他のページに同じCSSを充てる事が可能です。  
HTMLファイルから該当のCSSまでのパスをきちんと書かなければCSSは読み込まれません。

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>セレクタの練習1</title>
    <link rel="stylesheet" href="./assets/css/style.css">
  </head>
  <body>
    <p>この文字を赤にしたい。。</p>
  </body>
</html>
```

```css
/* style.css の中身 */
p {
  color: red;
}
```
<br><br><br>

---

<br><br><br>

## CSSのコメントの書き方

```css
/* コメントを書いて分かりやすいスタイルシートを書こう */

/*
    コメントは複数行でも記述できます。
    説明やメッセージなどを残せます。
*/
```
