# 3-2_CSSレイアウト_Flex基礎


# Flexbox（flexbox-basic.html）

WEBサイトをレイアウトする為に実装され、スマートフォンなどの端末でも最適で柔軟なレイアウトが実現できるプロパティです。
現状、Webサイトをレイアウトするために用いられるもっともメジャーなプロパティなので是非覚えておきましょう。


```html
<ul class="flexbox"> /* Flexコンテナー */
  <li>flexアイテム</li> /* Flexアイテム */
  <li>flexアイテム</li> /* Flexアイテム */
  <li>flexアイテム</li> /* Flexアイテム */
</ul>
```
```css
.flexbox {
  display: flex;
}
```


![](https://d2mxuefqeaa7sj.cloudfront.net/s_7DF33F8944F50DBBBCAFB844350AD0F55F2410F15DD00441E5D5AD6381F014B7_1522047628382_flex-container.png)




### メリット

- 親要素に`display: flex;`と指定すれば、子要素が横並びの対象となります。

### デメリット

- レガシーブラウザが対応していない場合がある。
    - IE9は未対応。IE10は`display:-ms-flexbox`。
    - IE11では`flex:1`ではなく`flex-grow：1`としなければならない。
    - Safari8 未満は`display: -webkit-flex`
    - iOS9 未満は`display: -webkit-flex`
    - Android 4.3 未満は`display: -webkit-box`
- モダンブラウザでも問題がある場合がある
    - [flexboxのバグに立ち向かう（flexboxバグまとめ）](https://qiita.com/hashrock/items/189db03021b0f565ae27)

---


## Flexboxのプロパティ

Flexbox関連のプロパティはたくさんあります。
無理にすべて覚えずに下記の表をうまく利用してレイアウトしてみてください。

### コンテナー用プロパティ

**flex-direction**　-　flexアイテムを並べる方向
**flex-wrap**　-　flexアイテムの折り返し
**justify-content**　-　左右中央
**align-item（align-self）** -　上下位置
**align-content**　-　行の揃え方

### アイテム用プロパティ

**flex-grow、flex-shrink、flex-basis**　-　伸縮系プロパティ
**order**　-　flexアイテムの順番



## **コンテナー用プロパティ**

#### flex-direction

Flexアイテムが並ぶ方向を決める為のプロパティ

| flex-direction | flexアイテムを並べる方向                                                                                            |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| row [default]  | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/57e22cbd-7ba4-5121-553f-cd9161ffbc02.png) |
| row-reverse    | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/38ee241c-5cba-2bad-d74b-d1754ace5967.png) |
| column         | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/08a6608c-ac40-c4d0-8ca7-95967c73d03b.png) |
| column-reverse | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/8be9ed65-fe5f-d1df-c274-3435a7297005.png) |




#### flex-wrap

コンテナー内でFlexアイテムを折り返すためのプロパティ

| flex-wrap        | flexアイテムの折り返し                                                                                             |
| ---------------- | --------------------------------------------------------------------------------------------------------- |
| nowrap [default] | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/efbb089e-4f4c-7ed4-84cb-1e845fcbdc0c.png) |
| wrap             | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/42444a24-4fb3-0860-a712-2de2d30e7516.png) |
| wrap-reverse     | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/39990523-9290-9615-1b0a-fc641121e3bd.png) |




#### justify-content

Flexアイテムを配置する際の間隔を設定するプロパティ

| justify-content      | 左右位置                                                                                                      |
| -------------------- | --------------------------------------------------------------------------------------------------------- |
| flex-start [default] | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/851768c5-3c07-af75-35b5-e150cb122e6a.png) |
| flex-end             | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/164bd56c-8241-a28e-2c19-0d377f25be43.png) |
| center               | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/0b819396-e77e-b31c-8765-a03a6acff0de.png) |
| space-between        | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/c8d7c93a-7c63-61c2-e1d1-c83b6f378952.png) |
| space-around         | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/150b3a82-c944-3106-4a93-09a24c69a04e.png) |





#### align-items

Flexアイテムを垂直に揃えるためのプロパティ

| align-items       | 上下位置                                                                                                      |
| ----------------- | --------------------------------------------------------------------------------------------------------- |
| flex-start        | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/8c35a611-6b8b-cf05-c8c1-971dbe6cb2f7.png) |
| flex-end          | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/a2af6bfc-0974-15ce-9f1d-e8567ac786a8.png) |
| center            | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/c03b27cc-f3c0-513e-8625-85840e587e32.png) |
| baseline          | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/fa411e4f-a014-8705-ff32-70cb3a3249e2.png) |
| stretch [default] | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/fbcb370a-7c06-530f-fc21-0391c22dbb7f.png) |
| （align-selfは省きます） |                                                                                                           |




#### align-content

Flexアイテムが2行以上になった場合にどう揃えるかを設定するプロパティ。
※「flex-wrap: wrap」が適用され、アイテムが2行になっている場合のみ有効

| align-content     | 行の揃え方                                                                                                     |
| ----------------- | --------------------------------------------------------------------------------------------------------- |
| stretch [default] | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/cdbf6492-60b1-9309-daeb-2624f0808c4a.png) |
| flex-start        | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/27f73e91-b30b-ffda-35c5-a61a2b653733.png) |
| flex-end          | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/137a34db-cc47-c2f9-94c4-71c2bc6c77c9.png) |
| center            | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/f5b1c0ea-e968-852e-90b0-4f2d88c6011e.png) |
| space-between     | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/2ecc0e1c-1bc7-dbf7-604a-2f1b58e53f1b.png) |
| space-around      | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/80987366-33c6-5442-bd7d-5ff4d4394f6a.png) |




----------
## 練習1

リンクなしのメニュー、`box-sizing: border-box` を用いてレイアウトしてください。



![](https://paper-attachments.dropbox.com/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1562407409523_+2019-07-06+19.03.20.png)


- 文字色：#333333
- メニュー全体の幅：656px
- メニュー全体をブラウザの左右中央に配置
- メニューのリストアイテムの横幅：120px
- 文字を中央寄せ
- リンク間の隙間：14px
- 余白：12px
- リストアイテムの背景色（通常時）：skyblue



## 練習2

上記の練習1を使ってリンク付きのメニューにしてみましょう。



![](https://paper-attachments.dropbox.com/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1562407582022_+2019-07-06+19.06.12.png)





- 背景色（マウスオン時）：palegreen



### 復習1

練習2を使って、全体をpadding20ピクセルの余白をつけて背景色 `#eeeeee` にしてください。
※ `box-sizing: border-box;` を用いてレイアウトしてください。



![](https://paper-attachments.dropbox.com/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1562407649118_+2019-07-06+19.07.18.png)


