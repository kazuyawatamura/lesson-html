# Flexboxでレイアウトしてみよう

<br><br><br>

# Flexbox

**flexbox-basic.html**

WEBサイトをレイアウトする為に実装され、スマートフォンなどの端末でも最適で柔軟なレイアウトが実現できるプロパティです。  
現状、Webサイトをレイアウトするために用いられるもっともメジャーなプロパティなので是非覚えておきましょう。


```html
<ul class="flexbox"> /* Container */
  <li>flexアイテム</li> /* Item */
  <li>flexアイテム</li> /* Item */
  <li>flexアイテム</li> /* Item */
</ul>
```
```css
.flexbox {
  display: flex;
}
```


![](https://laro.jp/lesson/images/lesson-css-flex1.png)

<br><br><br>

### メリット

- 親要素に`display: flex;`と指定すれば、子要素が横並びの対象となります。

<br><br><br>

### デメリット

- モダンブラウザでも問題がある場合がある
    - [flexboxのバグに立ち向かう（flexboxバグまとめ）](https://qiita.com/hashrock/items/189db03021b0f565ae27)
<br><br><br>
---
<br><br><br>

## Flexboxのプロパティ

Flexbox関連のプロパティはたくさんあります。  
無理にすべて覚えずに下記の表をうまく利用してレイアウトしてみてください。

<br><br><br>

### コンテナー用プロパティ

- **flex-direction**　-　flexアイテムを並べる方向
- **flex-wrap**　-　flexアイテムの折り返し
- **justify-content**　-　左右中央
- **align-item（align-self）** -　上下位置
- **align-content**　-　行の揃え方

<br><br><br>

### アイテム用プロパティ

- **flex-grow、flex-shrink、flex-basis**　-　伸縮系プロパティ
- **order**　-　flexアイテムの順番

<br><br><br>

## **コンテナー用プロパティ**

<br><br><br>

#### flex-direction

Flexアイテムが並ぶ方向を決める為のプロパティ

| flex-direction | flexアイテムを並べる方向                                                                                            |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| row [default]  | ![image.png](https://laro.jp/lesson/images/lesson-css-flex2.png) |
| row-reverse    | ![image.png](https://laro.jp/lesson/images/lesson-css-flex3.png) |
| column         | ![image.png](https://laro.jp/lesson/images/lesson-css-flex4.png) |
| column-reverse | ![image.png](https://laro.jp/lesson/images/lesson-css-flex5.png) |

<br><br><br>

#### flex-wrap

コンテナー内でFlexアイテムを折り返すためのプロパティ

| flex-wrap        | flexアイテムの折り返し                                                                                             |
| ---------------- | --------------------------------------------------------------------------------------------------------- |
| nowrap [default] | ![image.png](https://laro.jp/lesson/images/lesson-css-flex6.png) |
| wrap             | ![image.png](https://laro.jp/lesson/images/lesson-css-flex7.png) |
| wrap-reverse     | ![image.png](https://laro.jp/lesson/images/lesson-css-flex8.png) |

<br><br><br>

#### justify-content

Flexアイテムを配置する際の間隔を設定するプロパティ

| justify-content      | 左右位置                                                                                                      |
| -------------------- | --------------------------------------------------------------------------------------------------------- |
| flex-start [default] | ![image.png](https://laro.jp/lesson/images/lesson-css-flex9.png) |
| flex-end             | ![image.png](https://laro.jp/lesson/images/lesson-css-flex10.png) |
| center               | ![image.png](https://laro.jp/lesson/images/lesson-css-flex11.png) |
| space-between        | ![image.png](https://laro.jp/lesson/images/lesson-css-flex12.png) |
| space-around         | ![image.png](https://laro.jp/lesson/images/lesson-css-flex13.png) |

<br><br><br>

#### align-items

Flexアイテムを垂直に揃えるためのプロパティ

| align-items       | 上下位置                                                                                                      |
| ----------------- | --------------------------------------------------------------------------------------------------------- |
| flex-start        | ![image.png](https://laro.jp/lesson/images/lesson-css-flex14.png) |
| flex-end          | ![image.png](https://laro.jp/lesson/images/lesson-css-flex15.png) |
| center            | ![image.png](https://laro.jp/lesson/images/lesson-css-flex16.png) |
| baseline          | ![image.png](https://laro.jp/lesson/images/lesson-css-flex17.png) |
| stretch [default] | ![image.png](https://laro.jp/lesson/images/lesson-css-flex18.png) |
| （align-selfは省きます） |                                                                                                           |

<br><br><br>

#### align-content

Flexアイテムが2行以上になった場合、どう揃えるかを設定するプロパティ。
※「flex-wrap: wrap」が適用され、アイテムが2行になっている場合のみ有効

| align-content     | 行の揃え方                                                                                                     |
| ----------------- | --------------------------------------------------------------------------------------------------------- |
| stretch [default] | ![image.png](https://laro.jp/lesson/images/lesson-css-flex19.png) |
| flex-start        | ![image.png](https://laro.jp/lesson/images/lesson-css-flex21.png) |
| flex-end          | ![image.png](https://laro.jp/lesson/images/lesson-css-flex22.png) |
| center            | ![image.png](https://laro.jp/lesson/images/lesson-css-flex23.png) | | space-between     | ![image.png](https://laro.jp/lesson/images/lesson-css-flex24.png) |
| space-around      | ![image.png](https://laro.jp/lesson/images/lesson-css-flex25.png) |

<br><br><br>

----------
## 練習1

リンクなしのメニュー、`box-sizing: border-box` を用いてレイアウトしてください。



![](https://laro.jp/lesson/images/lesson-css-flex26.png)


- 文字色：#333333
- メニュー全体の幅：656px
- メニュー全体をブラウザの左右中央に配置
- メニューのリストアイテムの横幅：120px
- 文字を中央寄せ
- リンク間の隙間：14px
- 余白：12px
- リストアイテムの背景色（通常時）：skyblue

<br><br><br>

## 練習2

上記の練習1を使ってリンク付きのメニューにしてみましょう。



![](https://laro.jp/lesson/images/lesson-css-flex27.png)


- 背景色（マウスオン時）：palegreen

<br><br><br>

### 復習1

練習2を使って、全体をpadding20ピクセルの余白をつけて背景色 `#eeeeee` にしてください。
※ `box-sizing: border-box;` を用いてレイアウトしてください。



![](https://laro.jp/lesson/images/lesson-css-flex28.png)