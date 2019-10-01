# 4. CSS Animation

# transition


プロパティに変更があった時に、一定時間でプロパティを変化させる設定。
マウスオーバーなど単純な動きのアニメーションを実装する時に利用します。



![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522288460873_Kapture+2018-03-29+at+10.53.47.gif)


transition.html

    <div class="animation">アニメーション</div>


    .animation {
      width: 150px;
      height: 100px;
      background: orange;
      transition-property: all;
      transition-duration: .5s;
      transition-delay: 0s;
      transition-timing-function: ease;
    }
    .animation:hover {
      width: 300px;
      background: skyblue;
    }



## transition-property

どのプロパティにアニメーションを適用するか指定するプロパティ。

初期値は、 ```**all**` 

 `all`  を指定すると、全てのプロパティにアニメーションを適用する。
下の要素は  `background-color`  を指定しているため、それ以外のプロパティを変更しても
アニメーションが適用されません。

**all**

![全てのプロパティに対してアニメーションが適用](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291006012_Kapture+2018-03-29+at+11.36.31.gif)


**background-color**

![背景色のみアニメーションが適用](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291199753_Kapture+2018-03-29+at+11.39.54.gif)




## transition-duration

アニメーションが始まってから終わるまでの時間を指定します。
単位を秒数  `s` （またはミリ秒 `ms` ）で指定します。 `margin: 0;` のように単位は省略できません。必ず  `s` などをつけてください。

初期値は  `0s` 

例 
 `transition-duration: .5s;`   → 0.5秒

**3秒**


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291610651_Kapture+2018-03-29+at+11.46.18.gif)


**0.5秒**

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291665197_Kapture+2018-03-29+at+11.47.38.gif)



## transition-delay

アニメーションが開始するまでの遅延時間を指定するプロパティ。

初期値は、 `0` 


**1秒**

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291806943_Kapture+2018-03-29+at+11.49.44.gif)


**0秒**

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522291862165_Kapture+2018-03-29+at+11.50.53.gif)




## transition-timing-function

アニメーションのイージングを指定するプロパティ。

初期値は、  `ease` 


![via: https://developers.google.com/web/fundamentals/design-and-ux/animations/the-basics-of-easing?hl=ja](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522299879568_transition-timing-function.png)


**linear**
一定

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300294765_linear.gif)


**ease-out**
ゆっくり終わる

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300250520_ease-out.gif)


**ease-in**
ゆっくり始まる

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300364242_ease-in.gif)


**ease-in-out**
ゆっくり始まってゆっくり終わる

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300444293_ease-in-out.gif)


**cubic-bezier()**
3次ベジェ曲線のP1とP2を (x1, y1, x2, y2) で指定


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522300654127_Kapture+2018-03-29+at+14.17.24.gif)


http://cubic-bezier.com/


**ショートハンド**


    transition : all .5s 0s ease-out;

※遅延処理（delay）はあまり使わないので省略する事が多い。




参考：[CSSのみで実装するボタンデザインやホバーエフェクト 20＋α](https://www.nxworld.net/tips/css-only-button-design-and-hover-effects.html)



----------



# @keyframes と animation

@keyframes と animation プロパティを覚えると、CSSアニメーションにタイムラインの概念で要素をアニメーションさせる事ができ、演出の幅が広がります。


> @keyframes は、アニメーション中に到達すべきポイントであるキーフレーム (通過点) を明示することで、CSS animation の流れの中間地点をページ作者が制御することを可能にします。これにより、ブラウザにすべてを自動的に扱わせる場合よりも、アニメーションの流れの中間地点をより明確に制御することができます。
> 引用：[@keyframes – CSS | MDN](https://developer.mozilla.org/ja/docs/Web/CSS/@keyframes)



    @keyframes 任意の名前 {
      0% {
        CSSプロパティ:値;
      }
      100% {
        CSSプロパティ:値;
      }
    }


## 実例

keyframes.html 


    <div class="animation"></div>


    @keyframes translate {
      0% {
        opacity: 0;
        width: 0;
      }
      100% {
        opacity: 1;
        width: 400px;
      }
    }
    .animation {
      height: 100px;
      background-color: skyblue;
      animation-name: translate;
      animation-duration: .5s;
      animation-fill-mode: forwards;
    }





## animation プロパティ一覧
| **プロパティ**                   | **説明**                       |
| --------------------------- | ---------------------------- |
| `animation-name`            | アニメーションの名前                   |
| `animation-duration`        | アニメーションが始まって終わるまでの時間         |
| `animation-timing-function` | アニメーションの進行の度合い               |
| `animation-delay`           | アニメーションが始まる時間                |
| `animation-iteration-count` | アニメーションの繰り返し回数               |
| `animation-direction`       | アニメーションの再生方向                 |
| `animation-fill-mode`       | アニメーションの開始前、終了後のスタイル         |
| `animation-play-state`      | アニメーションの再生・停止                |
| `animation`                 | 8つのプロパティを一括指定できるショートハンドプロパティ |


**animation-name**

 `@keyframes`  で記述した名前を指定します。
 このプロパティだけではアニメーションはされません。


**animation-duration**

[+4. CSS Animation: transition-duration](https://paper.dropbox.com/doc/4.-CSS-Animation-transition-duration-DtyZIubguYF2WzOC6giz3#:uid=643459288697406061958319&amp;h2=transition-duration) 

例 
 `animation-duration: .5s;`   → 0.5秒


**animation-timing-function**

[+4. CSS Animation: transition-timing-function](https://paper.dropbox.com/doc/4.-CSS-Animation-transition-timing-function-DtyZIubguYF2WzOC6giz3#:uid=477585587404726305224850&amp;h2=transition-timing-function) 


**animation-delay**

[+4. CSS Animation: transition-delay](https://paper.dropbox.com/doc/4.-CSS-Animation-transition-delay-DtyZIubguYF2WzOC6giz3#:uid=597873418815953103465259&amp;h2=transition-delay) 


**animation-iteration-count**

アニメーションの繰り返し回数を指定できるプロパティです。
初期値は、 `1` 
 `animation-iteration-count: 3;`  とした場合は、3回アニメーションを繰り返します。

無限に繰り返したい場合は、値に `infinite` を指定します。


**animation-direction**

アニメーションの再生方向を指定できるプロパティです。
初期値は、 `normal` 


| **値**               | **説明**                     |
| ------------------- | -------------------------- |
| `normal`            | 指定した通り、再生                  |
| `reverse`           | 逆方向から再生                    |
| `alternate`         | 順方向、逆方向のアニメーションを交互に繰り返します。 |
| `alternate-reverse` | 逆方向、順方向のアニメーションを交互に繰り返します。 |


**animation-fill-mode**

アニメーションの開始前、終了後のスタイルの状態を指定できるプロパティ。
初期値は、 `none` 


| **値**       | **説明**                                 |
| ----------- | -------------------------------------- |
| `none`      | アニメーションの開始前、終了後には適用されません               |
| `forwards`  | 終了時のスタイルが、そのまま終了後にも適用されます              |
| `backwards` | 開始時のスタイルが、開始前にも適用されます。                 |
| `both`      | `forward`  と  `backwards`  の両方が適用されます。 |




    <ul>
      <li class="fill-mode none">none</li>
      <li class="fill-mode forwards">forwards</li>
      <li class="fill-mode backwards">backwords</li>
      <li class="fill-mode both">both</li>
    </ul>


    .fill-mode {
      text-align: center;
      line-height: 50px;
      height: 50px;
      background: black;
      animation-name: changeBgcolor;
      animation-duration: 3s;
      animation-delay: 10s;
    }
    .none {
      animation-fill-mode:none;
    }
    .forwards {
      animation-fill-mode:forwards;
    }
    .backwards {
      animation-fill-mode:backwards;
    }
    .both {
      animation-fill-mode:both;
    }
    @keyframes changeBgcolor {
      0% {
        background: red;
      }
      100% {
        background: orange;
      }
    }


![](https://d2mxuefqeaa7sj.cloudfront.net/s_D2733E69EAC834B8561E2B2BA9A5DC8E8070D76CCED2490693E19C6A38C31114_1534771769108_Kapture+2018-08-20+at+22.28.02.gif)


※アニメーション開始前は上から黒、黒、赤、赤ですが、終了後は、黒、オレンジ、黒、オレンジになっています。


**animation-play-state**

アニメーションの再生・停止を指定できるプロパティです。
初期値は   `running`  

running → アニメーション実行
paused → アニメーション停止


**ショートハンド**


    セレクタ名 {
      animation: animation-name animation-duration animation-timing-function animation-delay animation-iteration-count animation-direction animation-fill-mode animation-play-state;
    }


    セレクタ名 {
      animation: 名前 開始から終了までの時間 進行の度合い 開始時間 繰り返し回数 再生方向 開始前・終了後のスタイル 再生・停止;
    }

※順不同

・・・ただし、
 `animation-duration`  と  `animation-delay`  の2つのプロパティは両方とも秒数で指定するため、最初に記述した秒数が   `animation-duration`  で、次に記述した秒数が  `animation-delay`  と解釈される。



| **プロパティ**                   | **説明**          | **初期値**   | **値**                                                                                                             |
| --------------------------- | --------------- | --------- | ----------------------------------------------------------------------------------------------------------------- |
| `animation-name`            | 名前              | `none`    | 任意の文字列                                                                                                            |
| `animation-duration`        | 始まって終わるまでの時間を指定 | `0s`      | 非負の正数（単位は `s` , `ms` で指定）                                                                                         |
| `animation-timing-function` | 進行の度合いを指定       | `ease`    | `ease`  ,  `ease-in`  ,  `ease-out` ,  `linear`  ,  `cubic-bezier()`  ,  `step-start`  ,  `step-end` ,  `steps()` |
| `animation-delay`           | 始まる時間を指定        | `0s`      | 非負の正数（単位は `s` , `ms` で指定）                                                                                         |
| `animation-iteration-count` | 繰り返し回数を指定       | `1`       | 非負の正数（  `0.5`  などの指定も可）,  `infinite`                                                                              |
| `animation-direction`       | 再生方向を指定         | `normal`  | `normal`  ,  `reverse`  ,  `alternate`  ,  `alternate-reverse`                                                    |
| `animation-fill-mode`       | 開始前、終了後のスタイルを指定 | `none`    | `none`  ,  `forwards`  ,  `backwards`  ,  `both`                                                                  |
| `animation-play-state`      | 再生・停止を指定        | `running` | `running` ,  `paused`                                                                                             |


