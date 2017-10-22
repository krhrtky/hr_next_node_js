## 実際に動かしてみよう

* Node.jsの実行環境の準備
  * 作成したディレクトリ内で以下のコマンドを実行

    ```sh
    npm init -y
    ```

## WEBサーバーを立てる
* `server.js` を作成

  ```JavaScript
  'use strict'
  const http = require('http'); // ---①

  const hostname = '127.0.0.1';
  const port = 3000;

  const server = http.createServer((req, res) => { // ---②
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Hello Node.js!\n');
  });

  server.listen(port, hostname, () => { // ---③
    console.log(`Server running at http://${hostname}:${port}/`);
  });
  /**
  これでも動作する
  const server = http.createServer(function(req, res) {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Hello World\n');
   });

  server.listen(port, hostname, function() {
  console.log('Server running at http://' + hostname + ': + ' + port + '/');
  });
  */
  ```

* 以下のコマンドを実行

  `node server.js`

* ブラウザで( http://172.0.0.1:3000/ )にアクセス

---

① `Core Modules`(Node.jsに標準で搭載されている機能群)の１つ

  webサーバの構築用の機能

  jsファイルの中が使用するときは、

  `const <moduleName> = require('<moduleName>');`

②サーバの設定を作成

③サーバを起動
