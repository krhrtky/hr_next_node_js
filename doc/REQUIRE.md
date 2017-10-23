# Require

* 設定を他のJSファイルに分けて読み込む

## 設定を外部のjsファイルから読み込む

  ```JavaScript
  'use strict'
  const conf = {
    hostname : '127.0.0.1',
    port : 3000,
  };

  module.exports = conf; // ---④
  ```

## sample code:server.js

  ``` JavaScript
  'use strict'
  const http = require('http');
  // ADD
  const conf = require('./server-conf'); // ---⑤

  // CHANGE
  // const hostname = '127.0.0.1';
  // const port = 3000;
  const hostname = conf.hostname;
  const port = conf.port;

  const server = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Hello Node.js!\n');
  });

  server.listen(port, hostname, () => {
    console.log(`Server running at http://${hostname}:${port}/`);
  });
  ```

---

④ 変数(オブジェクト)を別のjsファイルで利用できるようにする。
  jsファイルにつき、1オブジェクト利用可能。

⑤ 自分で作成したJSファイルの値をrequireで利用するには、相対パスで記述する。
   拡張子「.js」は省略可能。
