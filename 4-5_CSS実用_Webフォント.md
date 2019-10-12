# Google FontsでWebフォントを表示してみよう

## Webフォントとは？

通常、Webサイトの字体（以下フォント）は、そのパソコンやスマホにあらかじめ入っているフォントデータを読み込んで表示されています。

一般的なパソコンでは、あらかじめインストールされているフォントは少なく、OSのバージョンにより、標準搭載されるフォントが異なるため、使用できるフォントも限られていました。

そのためデザイナーが意図したデザインで見せることが難しく、Webフォントが普及する前は画像化することが一般的でした。

**Windowsにインストールされているフォントの例**

| OSの標準搭載フォント   | フォント名                                      |
| ------------- | ------------------------------------------ |
| Windows 10    | UDデジタル教科書体・Yu Gothic UI                    |
| Windows 8.1   | 游ゴシック・游明朝                                  |
| Windows 7     | Meiryo UI                                  |
| Windows Vista | メイリオ                                       |
| Windows 初期〜   | MSゴシック MS明朝 / MSPゴシック MSP明朝 / MS UI Gothic |

※ 欧文フォントは他にもあります。

Macは欧文フォント日本語フォントともに多くのフォントが入っています。デザイナーが好んでMacを使用する理由のひとつです。
[macOS Sierra に組み込まれているフォント](https://support.apple.com/ja-jp/HT206872)



### Webフォントのメリット

ユーザーの環境に依存することなく、どのデバイスから見てもデザイナーの意図したデザインそのままに表示するためには、Webサーバー上のフォントデータを使う必要があります。

デザインを再現するために画像として文字を配置することも一般的に行われていますが、Webフォントを使うと、デバイスを問わずHTMLの文字（コピー&amp;ペーストできるテキスト）としてサイトに配置でき、検索に引っかかりやすくなりSEO対策としても有利になります。
さらにフォントサイズもCSSでコントロールできるため、レスポンシブデザインに対応しやすい、などの多くの利点があります。

* 導入が簡単
* 検索に引っかかりやすく、SEOに強い
* レスポンシブに対応し、異なるデバイスで可読性や視認性を担保できる


### Webフォントのデメリット

サーバーからフォントデータを読み込むので若干の遅延が発生します。
ただWebフォントのサービス（Google Fontsなど）の機能改善もあり、遅延することも少なくなってきました。

## 試してみよう

Google Fontsは無料でWebフォントを利用できます。
実務でもよく利用するサービスなので是非使い方を覚えておきましょう。
今回は、`Noto Serif JP` を表示させてみましょう。

**1. Google Fonts**
https://fonts.google.com/

**2. Languageを選択**
LanguageをJapaneseに変更します。
該当のフォントをクリックしてください。

![](https://paper-attachments.dropbox.com/s_57618050A23610DF813AD1198DA65210FE3FC11F977BF6FD2CA4F045448EE4DA_1570873721104__2019-10-12_18_41_31.png)

**3. SELECT THIS FONTを選択**

![](https://paper-attachments.dropbox.com/s_57618050A23610DF813AD1198DA65210FE3FC11F977BF6FD2CA4F045448EE4DA_1570873727064__2019-10-12_18_42_17.png)

**4. コードをコピペ**

画面右下に `1 Family Selected` という黒帯をクリックすると選択したフォント情報がでてきます。

そこに専用のHTMLコードとCSSコードが表示されるのでそれをコピペします。

![](https://paper-attachments.dropbox.com/s_57618050A23610DF813AD1198DA65210FE3FC11F977BF6FD2CA4F045448EE4DA_1570873730258__2019-10-12_18_42_30.png)




**web-font.html**

`<meta>` の中に `<link>` を記述します。
```html
<link href="https://fonts.googleapis.com/css?family=Noto+Serif+JP&display=swap" rel="stylesheet">
```

```html
<h1 class="webfonts">Webフォント、こんにちは</h1>
```

```css
.webfonts {
  font-family: 'Noto Serif JP', serif;
}
```