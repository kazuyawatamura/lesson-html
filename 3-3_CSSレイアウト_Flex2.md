# CSSレイアウト Flex伸縮系のプロパティなど
 
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

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522051980707_flex-grow1.png)




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

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522052024358_flex-grow2.png)




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

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522052029288_flex-grow3.png)


#### 参考1
https://codepen.io/cshool/pen/rQJdbg

#### 参考2
https://residence.nikkei.co.jp/

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522806000794_Kapture+2018-04-04+at+10.02.25.gif)


#### 参考3
https://www.quantamagazine.org/universal-quantum-phenomenon-found-in-superconductors-20181119/

![](https://d2mxuefqeaa7sj.cloudfront.net/s_A6FC300D63F4B84E73A02866CF60B09B657A6400DA32DA4CB69231FF6ED8C79A_1542849068523_+2018-11-22+10.10.41.png)

![](https://d2mxuefqeaa7sj.cloudfront.net/s_A6FC300D63F4B84E73A02866CF60B09B657A6400DA32DA4CB69231FF6ED8C79A_1542849105758_+2018-11-22+10.11.28.png)





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

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522054562528_flex-shrink1.png)


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

#### 参考1
https://codepen.io/cshool/pen/yQvjNw

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522055935628_animation.gif)


 `flex-shrink: 0;` を指定した場合、どれだけコンテナーが狭くなってもこれ以上は縮まない。

`flex-shrink: 2;` 以上の数値を指定した場合、その数値の倍速で縮む。

> 例： `flex-shrink: 4;`   → 4倍の速度で縮む。


#### 参考2

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522806025486_Kapture+2018-04-04+at+10.03.41.gif)




### flex-basis
Flexアイテムの進行方向に対する `width` のようなもの。
 `flex-direction: column;`  で縦ならびになった際は、heightと同じ効果。



### 伸縮系flexアイテムのショートハンド

覚えにくいと思うので、こういうのがあると頭の片隅に入れておいてください。

```css
li {
  flex: 0 1 auto;
  /* grow shrink basis */
}
```


### order

| order       | 順番の指定                                                                                                     |
| ----------- | --------------------------------------------------------------------------------------------------------- |
| 0 [default] | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/18a379a6-85e3-6261-725a-2de585399fbb.png) |
| 1           | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/8d6fc25e-6e70-5f67-77c6-361b79676fe7.png) |
| -1          | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/d474b306-c991-d900-2c14-b522110d9d0c.png) |
| 9           | ![image.png](https://qiita-image-store.s3.amazonaws.com/0/74438/074d1d04-f71e-51d6-ce4b-c14a610e6424.png) |



[【参考】Flexbox playground](https://codepen.io/enxaneta/pen/adLPwv)


## 練習1
![](https://paper-attachments.dropbox.com/s_A6FC300D63F4B84E73A02866CF60B09B657A6400DA32DA4CB69231FF6ED8C79A_1562410844855_+2019-07-06+20.00.32.png)

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



## 練習2
![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522118985431_flex-3.png)

- 余白や色など指定はなし