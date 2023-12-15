## MEMO
### 변수이름
소문자,언더바 -> 값을 가지는 변수  
낙타형 -> 함수형 변수
<br />

## 컴포넌트 역할  

컴포넌트 | 역할
-- | -- 
NavBar | 애플리케이션의 메뉴를 담당하고, 각 메뉴에 따라 적절한 컴포넌트를 호출한다.  
Profile | 프로필 페이지는 웹 애플리케이션 운영자의 이력이 들어간다.
<br />

## 서버
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

## setup(props,context)
props와 context라는 두 개의 매개변수를 가질 수 있다.  
- **props**  
        setup함수는 컴포넌트가 Props를 인지한 후 호출이 되므로 props에 대한 처리 가능  
        반응성이 있어서 props가 변경되면 화면이 변경된다.

- **context**   
        속성으로 attrs, slots, emit을 가지고 있다.  
        - attrs : Non-Prop  
        - slots : 슬롯에 대한 프록시 객체  
        - emit : 이벤트를 발생시킬 수 있는 함수    

    반응성이 없으므로 구조 분해 할당 가능하다   
        ```
        setup(props, { attrs, slots, emit })
        ```  
<br />

## computed  
데이터를 필요에 따라 변환하고 싶을 때 사용한다.  
반응성을 가지므로 템플릿의 선언적 변수로 많이 사용된다.  
일반적으로 getter 함수를 정의하여 ref 객체를 반환하지만, get/set 함수를 정의하여 쓰기 가능한 ref객체를 생성할 수도 있다.
```js
const index = ref(0)
const num = computed({ get: () => index.value, set: v => { index.value = v+1 }})
```
위와 같이 computed ref 객체를 생성하고 num,value에 값을 넣으면 자동으로 1이 올라간다.



