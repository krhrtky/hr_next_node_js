# npm

## [npm](https://www.npmjs.com/)

* CommonJS のパッケージマネージャー

	java の `maven` のようなもの

* Node の workspace を作成する( `Core Modules` を使えるようにする)
	```
	$ npm init
	```

* ライブラリをインストールするには、以下のコマンド

	```
	$ npm install <library name> --save
	```

* ライブラリを使用するときには、 `Core Modules` と同様に `require()` でインポートする。


## CommonJS
* サーバーサイドなどのウェブブラウザ環境外におけるJavaScriptの各種仕様を定めることを目標としたプロジェクトである。(Wikipediaより)

* クライアント(ブラウザ)では`<script>`の読み込み順で解決。

* 例) jQuery とプラグイン

* サーバには、`<script>`はないので、読み込み順を決めないといけない。
