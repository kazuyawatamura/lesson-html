
# 疑似要素（before-after.html）




![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522207364851_HTML.png)


HTMLには書かれていない要素もどき（疑似的に）をCSSで作ることが可能になります。
（要素とはHTMLの文章や画像の事ですね。）

そして疑似要素をマスターするとより幅広い表現が可能になります。
たとえば、、、


![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522207977692_beforeafter1.png)



```html
<div class="before">こんにちは</div>
<div class="after">さようなら</div>
```
```css
.before::before {
  content: "[hello]";
  margin-right: 10px;
}
.after::after {
  content: "[Goodbye]";
  margin-left: 10px;
}
```

- ::before ： 要素の直前に内容（content）を追加
- ::after　： 要素の直後に内容（content）を追加



## 具体的な活用方法

### テキストをかぎかっこで囲む

```html
<div class="example1">これはサンプルテキストです。</div>
```
```css
.example1::before{
  content: '『';
  color: orange;
}

.example1::after{
  content: '』';
  color: orange;
}
```


### タイトル文の英字を入れる

```html
<h1 class="example2">タイトル</h1>
```
```css
.example2 {
  text-align: center;
}

.example2::before{
  content: 'Title';
  color: palegreen;
  font-size: 20px;
  display: block;
}
```

疑似要素は初期値ではインライン要素のため、 `display: block;`  を入れて前後に改行が入るようにします。

### 【Extra】data属性を使ってタイトルを入れてみる

```html
<h1 data-title="title" class="example3">タイトル</h1>
```
```css
.example3 {
  text-align: center;
}
.example3::before{
  content: attr(data-title);
  color: palegreen;
  font-size: 20px;
  display: block;
}
```


### 絶対配置（position: absolute;）で、疑似要素を好きな位置に配置する

かなり便利で表現方法が増えるので是非覚えましょう。

```html
    <h1 class="absolute">ここにタイトルを書きます</h1>
```
```css
    .absolute {
      position: relative;
    }
    .absolute::before {
      content: "";
      position: absolute;
      top: -32px;
      left: -32px;
      background: url(./assets/images/image/ico-new.png);
      width: 42px;
      height: 42px;
    }
```

![ico-new.png](https://d2mxuefqeaa7sj.cloudfront.net/s_3AFFAD81B710F086AB22545D7AB6A184015C245587269DFF7E16C5AFB7C20C7D_1522893931247_ico-new.png)



## 練習
https://www.dropbox.com/s/ii3ft2n116vyc5p/icon.zip?dl=0



![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522224752565_beforeafter2.png)



```html
<ul class="menu-before">
  <li class="home"><a href="#">ホーム</a></li>
  <li class="boss"><a href="#">社長メッセージ</a></li>
  <li class="company"><a href="#">会社概要</a></li>
  <li class="recruit"><a href="#">新卒採用</a></li>
  <li class="other"><a href="#">その他</a></li>
</ul>
```

### ヒント

![](https://d2mxuefqeaa7sj.cloudfront.net/s_CC1F790C680E94AE4D7E9778AAA44D521592E7AC2AC6A52752CCFB8ED2A216CE_1522232694697_beforeafter3.png)



