
# パスについて

パスとは、特定のファイルやフォルダーが置いてある場所のことです。
Webサイトには画像やCSSなど外部ファイルがたくさんあります。
それらをパスを使って繋げていきWebサイトができていきます。



## まず画像を表示してみよう

![](https://paper-attachments.dropbox.com/s_2C690E47BA11F144E8378F284F5ED9792FA67D3EBB48367FF6A47D8A094E64EC_1569980386188_lesson-html-path-cat1.jpg)

```<img src="cat.jpg">```


### 属性と値

要素に情報を付加するもの。
srcに対して、値を与えてあげる働きがあります。


## 絶対パスと相対パス

- 絶対パス：「http://」から始まるパス（例：https://amazon.co.jp）
    - 「東京都世田谷区・・」から始まる住所の様なパス
- 相対パス：「./」や「../」から始まるパス
    - 自分から「信号を右に曲がり、階段を上がり・・」という現在地と対象を相対的に見るパス


### 違うファイルにリンクを指定してみよう

#### 【/】（スラッシュ）

階層を1つ深くなります。
※Windowsでは¥マークで表されます。

#### 【../】（ドット、ドット、スラッシュ）
階層を上に上がります。

### 例

![](https://paper-attachments.dropbox.com/s_6DC39C02081D2F0F89C1BB40AC805C4C3DCC6DA94D1CE0AB6A7FB3CF3041E463_1569979237558_link1.png)

#### 【example-a.html】に【images】フォルダーの中の【photo.jpg】を表示させる場合

example-a.htmlに下記を入力
```<img src="images/photo.jpg" alt="">```


#### 問題

回答するのはパスだけで構いません。
（src=""などの属性は不要です）

![](https://d2mxuefqeaa7sj.cloudfront.net/s_3066FA23A18E1433BC4D48A1112B9F0C6A766C9E0917C880D3A50377E5D58EB4_1520603381995_link2.png)

問1：【example-a.html】から【example-b.html】にリンクを貼る場合

問2：【example-b.html】から【example-c.html】にリンクを貼る場合

問3：【example-c.html】に【photo.jpg】を表示させる場合


#### 参考
[【初心者向け】絶対パスと相対パスの違いをイラストを使って解説！](https://webliker.info/78726/)
