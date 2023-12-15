# 서버
```bash
npm install sqlite3
npm install express
npm install cors
```

### Sqlite3
**SQL 데이터베이스 엔진**  
메모리를 바탕으로 데이터베이스를 구성할 수 있으며, 파일을 생성하여 보존이 가능한 데이터베이스도 손쉽게 생성할 수 있다.

### Express
**Node.js를 위한 경량화 웹 프레임워크**  
웹 애플리케이션을 개발함에 있어 간단한 서버가 필요하거나, 백엔드가 필요할 때 자주 사용한다.

> express + sqlite3은 Node.js 서버를 구성할 때 가장 많이 쓰이는 조합으로 REST를 구현하는데 매우 편리하다.

### CORS  
웹 서버에 존재하는 리소스에 대해 다른 도메인이 접근하는 것을 막아주거나 허용하는 정책 
```js  
// database/index.js
app.use(cors())
```
포트가 3000, 8000으로 다르기 때문에 CORS 기본정책에 의해 데이터를 주고받을 수 없다.  
cors 미들웨어를 불러와 express와 연동해주면서 모든 Cross Origin 요청을 허용한다.  
터미널에서 ```node index.js```를 실행하면 database 서버가 실행된다.
<br />