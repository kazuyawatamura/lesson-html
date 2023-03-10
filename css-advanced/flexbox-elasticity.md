- [Flexboxアイテムの伸縮系プロパティ](#flexboxアイテムの伸縮系プロパティ)
  - [Flexアイテムの伸縮系プロパティ](#flexアイテムの伸縮系プロパティ)
    - [flex-grow](#flex-grow)
      - [参考1](#参考1)
      - [参考2](#参考2)
      - [参考3](#参考3)
    - [flex-shrink](#flex-shrink)
      - [参考1](#参考1-1)
      - [参考2](#参考2-1)
    - [flex-basis](#flex-basis)
    - [伸縮系flexアイテムのショートハンド](#伸縮系flexアイテムのショートハンド)
    - [order](#order)
  - [練習1](#練習1)
  - [練習2](#練習2)


# Flexboxアイテムの伸縮系プロパティ

<br><br><br>

## Flexアイテムの伸縮系プロパティ

レイアウトする際に、必要なプロパティではありませんが、  
デバイス毎に横幅が伸び縮みして、可変する場合に効果があります。


| flex-grow,flex-shrink,flex-basis | 伸縮系プロパティ  |
| -------------------------------- | --------- |
| flex-grow                        | 初期値： 0    |
| flex-shrink                      | 初期値： 1    |
| flex-basis                       | 初期値： auto |



```html
<ul class="flexbox"> /* container */
  <li>flexアイテム</li> /* Item */
  <li>flexアイテム</li> /* Item */
  <li>flexアイテム</li> /* Item */
</ul>
```
<br><br><br>

### flex-grow
コンテナー内の余った領域を、各アイテムにどう分配するかの割合。

```css
.flexbox {
  display: flex;
  width: 700px;
  padding: 16px;
  background-color: #EEE;
}
li {
  width: 100px;
  height: 100px;
  margin-right: 14px;
  background-color: palegreen;
  /* flex-grow: 0; */
}
```

<br>

![](https://laro.jp/lesson/images/lesson-css-flexgrow1.png)

<br>


2番目のFlexアイテムに  `flex-grow: 1`  を設定した。

```css
li {
  width: 100px;
  height: 100px;
  margin-right: 14px;
  background-color: palegreen;
  /* flex-grow: 0; */
}
li:nth-child(2) {
  flex-grow: 1;
}
```
<br>

![](https://laro.jp/lesson/images/lesson-css-flexgrow2.png)

<br>


2番目のFlexアイテムに  `flex-grow: 2`  を設定し、4番目のFlexアイテムに  `flex-grow: 1`  を設定した。

```css
li {
  width: 100px;
  height: 100px;
  margin-right: 14px;
  background-color: palegreen;
  /* flex-grow: 0; */
}
li:nth-child(2) {
  flex-grow: 2;
}
li:nth-child(4) {
  flex-grow: 1;
}
```

<br>

![](https://laro.jp/lesson/images/lesson-css-flexgrow3.png)

<br><br><br>

#### 参考1
https://codepen.io/cshool/pen/rQJdbg

<br><br><br>

#### 参考2
https://residence.nikkei.co.jp/

![](https://laro.jp/lesson/images/lesson-css-flexgrow4.gif)

<br><br><br>

#### 参考3
https://www.quantamagazine.org/universal-quantum-phenomenon-found-in-superconductors-20181119/

![](https://laro.jp/lesson/images/lesson-css-flexgrow5.png)

![](https://laro.jp/lesson/images/lesson-css-flexgrow6.png)


<br><br><br>


### flex-shrink
縮む割合をコンテナー内の余った領域から、その割合をどう分配するか。  
コンテナーが小さすぎる場合にのみ効果があります。

```html
<ul class="flexbox">
  <li>flexアイテム</li>
  <li>flexアイテム</li>
  <li>flexアイテム</li>
  <li>flexアイテム</li>
  <li>flexアイテム</li>
  <li>flexアイテム</li>
</ul>
```
```css
li {
  width: 100px;
  height: 100px;
  margin-right: 14px;
  background-color: palegreen;
  /* flex-shrink: 1; */
}
```
<br>

![](https://laro.jp/lesson/images/lesson-css-flexgrow7.png)

<br>
2番目のFlexアイテムに  `flex-shrink: 0`  を設定し、4番目のFlexアイテムに  `flex-shrink: 4`  を設定した。

```css
li {
  width: 100px;
  height: 100px;
  margin-right: 10px;
  background-color: palegreen;
  /* flex-shrink: 1; */
}
li:nth-child(2) {
  flex-shrink: 0;
}
li:nth-child(4) {
  flex-shrink: 4;
}
```

<br><br><br>

#### 参考1
https://codepen.io/cshool/pen/yQvjNw

![](https://laro.jp/lesson/images/lesson-css-flexgrow8.gif)


 `flex-shrink: 0;` を指定した場合、どれだけコンテナーが狭くなってもこれ以上は縮まない。

`flex-shrink: 2;` 以上の数値を指定した場合、その数値の倍速で縮む。

> 例： `flex-shrink: 4;`   → 4倍の速度で縮む。

<br><br><br>

#### 参考2

![](https://laro.jp/lesson/images/lesson-css-flexgrow9.gif)

<br><br><br>

### flex-basis
Flexアイテムの進行方向に対する `width` のようなもの。
 `flex-direction: column;`  で縦ならびになった際は、heightと同じ効果。

<br><br><br>

### 伸縮系flexアイテムのショートハンド

覚えにくいと思うので、こういうのがあると頭の片隅に入れておいてください。

```css
li {
  flex: 0 1 auto;
  /* grow shrink basis */
}
```
<br><br><br>

### order

| order       | 順番の指定                                                                                                     |
| ----------- | --------------------------------------------------------------------------------------------------------- |
| 0 [default] | ![image.png](https://laro.jp/lesson/images/lesson-css-flexgrow10.png) |
| 1           | ![image.png](https://laro.jp/lesson/images/lesson-css-flexgrow11.png) |
| -1          | ![image.png](https://laro.jp/lesson/images/lesson-css-flexgrow12.png) |
| 9           | ![image.png](https://laro.jp/lesson/images/lesson-css-flexgrow13.png) |

[【参考】Flexbox playground](https://codepen.io/enxaneta/pen/adLPwv)

<br><br><br>

## 練習1
![](https://laro.jp/lesson/images/lesson-css-flexgrow14.png)

- 文字色：#FFFFFF
- メニュー全体の幅：ブラウザの幅に準ずる
- メニュー全体をブラウザの両端に合わせる
- リンク間の隙間：ブラウザの幅に準ずる
- リンクの背景色（奇数）：#4DC5DE
- リンクの背景色（偶数）：#31EDFF
- アイテムの余白：20px
- 文字色（マウスオン時）：#333333
- リンクの背景色（マウスオン時）：#C9FF31
- 枠線：1px、　実線、　#333333
- コンテナーの高さ：400px
- コンテナーの背景色：#EEEEEE
- コンテナーの高さに対してアイテムを均等に分散配置する

<br><br><br>

## 練習2
![](https://laro.jp/lesson/images/lesson-css-flexgrow15.png)

- 余白や色など指定はなし