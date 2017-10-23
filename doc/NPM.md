# npm

## [npm](https://www.npmjs.com/)とは、

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
