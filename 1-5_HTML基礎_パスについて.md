
# パスについて

パスとは、特定のファイルやフォルダーが置いてある場所のことです。
Webサイトには画像やCSSなど外部ファイルがたくさんあります。
それらをパスを使って繋げていきWebサイトができていきます。



## まず画像を表示してみよう

![](https://paper-attachments.dropbox.com/s_2C690E47BA11F144E8378F284F5ED9792FA67D3EBB48367FF6A47D8A094E64EC_1569980386188_lesson-html-path-cat1.jpg)

```html
<img src="./cat.jpg">
```


### 属性と値

要素に情報を付加するもの。
srcに対して、値を与えてあげる働きがあります。


## 絶対パスと相対パス

- 絶対パス：「http://」から始まるパス（例：https://amazon.co.jp）
    - 「東京都世田谷区・・」から始まる住所の様なパス
- 相対パス：「./」や「../」から始まるパス
    - 自分から「信号を右に曲がり、階段を上がり・・」という現在地と対象を相対的に見るパス


### 違うファイルにリンクを指定してみよう

#### 【./】（ドット、スラッシュ）

「同じ階層の」という意味です。
パスの頭に付けます。

**例**
```html
./images/flowers.jpg
```
**同じ階層**にある「images」フォルダーの中の「flowers.jpg」というファイル名の画像、という意味になります。

ただややこしい事に `./` は無くても大丈夫です。


#### 【/】（スラッシュ）

階層を1つ深くなります。
※Windowsでは¥マークで表されます。

#### 【../】（ドット、ドット、スラッシュ）
階層を上に上がります。

### 例

![](https://paper-attachments.dropbox.com/s_4AFE1D42921B49A1323F81806A5D8CA9E5A3178118A99D50F44A4B49B29FB3D8_1570888909145_link1.png)


#### 【example-a.html】に【images】フォルダーの中の【photo.jpg】を表示させる場合

```<img src="./images/photo.jpg" alt="">```

example-a.htmlに上記を入力すると、

* 同じ階層にあるimagesフォルダーの中の
* photo.jpgというファイル名の画像を表示させる

という指定になります。



#### 問題

回答するのはパスだけで構いません。
（src=""などの属性は不要です）

![](https://paper-attachments.dropbox.com/s_4AFE1D42921B49A1323F81806A5D8CA9E5A3178118A99D50F44A4B49B29FB3D8_1570888913424_link2.png)

**問1**：【example-a.html】から【example-b.html】にリンクを貼る場合

**問2**：【example-a.html】から【example-c.html】にリンクを貼る場合

**問3**：【example-c.html】に【photo.jpg】を表示させる場合


#### 参考
[【初心者向け】絶対パスと相対パスの違いをイラストを使って解説！](https://webliker.info/78726/)
