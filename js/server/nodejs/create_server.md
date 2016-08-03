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

### 관련 레퍼런스
>
- http.createServer([requestListener])는 http.Server의 새 인스턴스를 리턴한다.
- http.Server class는 net.Server를 상속하고 추가적인 이벤트를 갖는다.
- net.Server class는 TCP나 로컬 서버를 생성하는데 사용된다. net.Server는 EventEmitter이다.
- The EventEmitter class is defined and exposed by the events module
- EventEmitter class는 'events' 모듈에 의해 정의되고 드러난다(번역 이게 최선?).
 -모든 EventEmitter는 새로운 listener가 추가될 때 'newListener'를, 존재하는 listener가 제거될 때 'removeListener'를 발행한다(번역..;;).

### 추가할 내용
- 소켓
- TCP/IP