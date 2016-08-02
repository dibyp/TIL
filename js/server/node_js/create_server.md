###### Aend's TIL

# Node.js

### 서버 생성

```js
// http 모듈을 부르기
const http = require('http');

// local IP 주소와 포트 번호 hostname, port 각각의 변수에 할당 
const hostname = '127.0.0.1';
const port = 3000;

// http의 createServer 매소드를 통해 응답 값 세팅 및 서버 생성
const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

// 생성된 서버로 하여금 특정 IP 주소의 특정 port를 지켜보도록 시킴
server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```