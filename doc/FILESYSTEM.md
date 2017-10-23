# fileSystem

* jsonファイルを読み込む

## fileSystemを利用する
```Json
"conf" : {
  "hostname" : "127.0.0.1",
  "port" : 3000
}
```

## server.js を書き換える
``` JavaScript
'use strict'
const http = require('http');
// ADD
const fs = require('fs'); // ---6
// CHANGE
const conf = (fs.existsSync('./server-config.json')) // ---7
  ? JSON.parse(fs.readFileSync('./server-conf.json', 'utf-8')); // ---8
  : {
      hostname : '127.0.0.1',
      port : 9000,
    };

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

ⅵ. fileSystemは、 `Core Modules` で `fs` で利用可能。

ⅶ. ファイルが存在するか確認する。

ⅷ. ファイルを読み込む。
