# 【練習用】実際にマークアップしてみよう

<br><br><br>

## 演習A

このテキストにHTMLでタグ付けしてみましょう。  

```
Anker（アンカー）

モバイルバッテリー・充電器・スピーカー・イヤホン・ケーブルならAnker(アンカー)公式オンラインストア｡iPhone・AndroidやiPad・Macbook等のスマホ・タブレット・パソコンにおすすめの製品を取り揃えています｡USB PDや急速充電情報も満載｡

製品カテゴリから探す
モバイルバッテリー
急速充電器
ケーブル

	モバイルバッテリー
	お使いの機器へフルスピード充電が可能。いつでもどこでも利用できるモバイルバッテリー。

		大容量（10000mAh〜）
		スマホへ約3〜4回のフル充電。コンパクト＆大容量を追求。持ち運びに適したコンパクトサイズながら大容量を実現。

		バッテリーケース
		Anker独自の技術をスマートフォンケースに搭載。

	急速充電器
	Anker独自の充電技術を搭載。細部にもこだわった高品質な急速充電器。

		USB急速充電器（卓上式）
		複数機器を同時に、フルスピードで。

		ワイヤレス充電器
		使い方は、置くだけ。シンプルかつ便利に充電。

	ケーブル
	究極の高耐久とフルスピード充電を実現。断線しにくく､頼りになるAnkerのケーブル。

		ライトニングUSBケーブル
		Apple社に許可を受けた証であるMFi認証を取得。iPhoneやiPadなどに急速充電だけでなくデータ転送や同期が可能です。

		Micro USBケーブル
		どんなMicro USB機器にも使えて、高耐久。
```

<br><br><br>

## 演習B

演習Aが終わったら下記のテキストもマークアップしてみましょう。

```
Apple

Appleは、iPhone、iPad、Mac、Apple Watch、iOS、OS X、watchOSといったイノベーションで世界をリードしています。
製品の情報も、購入も、サポートも、すべてAppleのウェブサイトでどうぞ。（2020年5月1日）

テーマ・製品カテゴリから探す
Mac
iPad
iPhone

	Mac
	新しいMacBook、iMac、Mac Pro、ほかにもいろいろ。Macの世界の魅力を紹介します。製品の情報も、購入も、サポートも、すべてAppleのウェブサイトでどうぞ。

		MacBook
		驚くほど薄くて軽い新しいMacBookは、目を奪う12インチRetinaディスプレイ、新設計のキーボード、新しい感圧タッチトラックパッドを搭載しています。

		MacBook Air
		新しいMacBook Airは、第5世代のIntel Coreプロセッサと一日中使い続けられるバッテリーを搭載。でも、圧倒的な薄さと軽さはそのままです。

		MacBook Pro
		最新世代のIntelプロセッサ、まったく新しいグラフィックス、より速くなったフラッシュストレージ。MacBook Proのパワーとパフォーマンスがさらに進化します。

	iPad
	iPad ProとiPad mini 4が登場したiPadの世界を紹介します。製品の情報も、購入も、サポートも、すべてAppleのウェブサイトでどうぞ。

		iPad Pro
		iPad Pro。薄く。軽く。壮大

		iPad Air 2
		iPad Air 2。軽いボディ。ヘビーなパワー。

		iPad mini 4
		手放せない性能。手放す必要がない薄さと軽さ。

	iPhone
	iPhone 6sは、これまでで最もパワフルなテクノロジーと最も直感的なオペレーティングシステムを搭載しています。そのiPhoneの魅力をご紹介します。

		iPhone 6s
		唯一変わったのは、そのすべて。

		iPhone 6
		シルバーまたはスペースグレイから選べます

〒106-6140
東京都港区六本木6丁目10番1号

Copyright © 2020 Apple Inc. All rights reserved.
```


<details>
<summary>サンプルHTML</summary>
<pre>
<code>

<header>
	<h1>Apple</h1>
	<p>Appleは、iPhone、iPad、Mac、Apple Watch、iOS、OS X、watchOSといったイノベーションで世界をリードしています。<br>
	製品の情報も、購入も、サポートも、すべてAppleのウェブサイトでどうぞ。<time datetime="2020-05-01">（2020年5月1日）</time></p>
	<nav>
		<p>テーマ・製品カテゴリから探す</p>
		<ul>
			<li><a href="#">Mac</a></li>
			<li><a href="#">iPad</a></li>
			<li><a href="#">iPhone</a></li>
		</ul>
	</nav>
</header>
<main>
	<!-- Mac -->
	<section>
		<h2>Mac</h2>
		<p>新しいMacBook、iMac、Mac Pro、ほかにもいろいろ。Macの世界の魅力を紹介します。製品の情報も、購入も、サポートも、すべてAppleのウェブサイトでどうぞ。</p>
		<section>
			<h3>MacBook</h3>
			<p>驚くほど薄くて軽い新しいMacBookは、目を奪う12インチRetinaディスプレイ、新設計のキーボード、新しい感圧タッチトラックパッドを搭載しています。</p>
		</section>
		<section>
			<h3>MacBook Air</h3>
			<p>新しいMacBook Airは、第5世代のIntel Coreプロセッサと一日中使い続けられるバッテリーを搭載。でも、圧倒的な薄さと軽さはそのままです。</p>
		</section>
		<section>
			<h3>MacBook Pro</h3>
			<p>最新世代のIntelプロセッサ、まったく新しいグラフィックス、より速くなったフラッシュストレージ。MacBook Proのパワーとパフォーマンスがさらに進化します。</p>
		</section>
	</section><!-- /Mac -->
	<!-- iPad -->
	<section>
		<h2>iPad</h2>
		<p>iPad ProとiPad mini 4が登場したiPadの世界を紹介します。製品の情報も、購入も、サポートも、すべてAppleのウェブサイトでどうぞ。</p>
			<section>
				<h3>iPad Pro</h3>
				<p>iPad Pro。薄く。軽く。壮大</p>
			</section>
			<section>
				<h3>iPad Air 2</h3>
				<p>iPad Air 2。軽いボディ。ヘビーなパワー。</p>
			</section>
			<section>
				<h3>iPad mini 4</h3>
				<p>手放せない性能。手放す必要がない薄さと軽さ。</p>
			</section>
	</section>
	<!-- iPhone -->
	<section>
		<h2>iPhone</h2>
		<p>iPhone 11は、これまでで最もパワフルなテクノロジーと最も直感的なオペレーティングシステムを搭載しています。そのiPhoneの魅力をご紹介します。</p>
			<section>
				<h3>iPhone 11</h3>
				<p>唯一変わったのは、そのすべて。</p>
			</section>
			<section>
				<h3>iPhone 11 Pro Max</h3>
				<p>シルバーまたはスペースグレイから選べます</p>
			</section>
	</section>
</main>
<footer>
	<address>
		〒106-6140<br>
		東京都港区六本木6丁目10番1号
	</address>
	<small>Copyright © 2020 Apple Inc. All rights reserved.</small>
</footer>

</code>
</pre>
</details>

[サンプルHTMLはこちらからダウンロード](/lesson-html/assets/code/apple_outline.html)

<br><br><br>

## チェックサービス

**Markup Validation Service**  
[https://validator.w3.org/nu/#textarea](https://validator.w3.org/nu/#textarea)

**HTML 5 Outliner**  
[http://gsnedders.html5.org/outliner/](https://validator.w3.org/nu/#textarea)