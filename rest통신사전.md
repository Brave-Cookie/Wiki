# Rest API 통신 사전

### 프론트 - 백 협업할때 형식 정해놓기

<br>

## Rest 통신 규칙

### Restful HTTP Method

- [Rest 통신 기본 개념](https://one-it.tistory.com/entry/RESTful-API-%EC%84%A4%EA%B3%84-%EA%B7%9C%EC%B9%99)
- [POST와 GET의 차이](https://im-developer.tistory.com/166)

|HTTP Method|설명|
|---|---|
|GET|조회(받겠다)|
|POST|리소스 생성(보내겠다)|
|PUT|리소스 전체 갱신(넣겠다)|
|PATCH|리소스 부분 갱신(붙이겠다)|
|DELETE|리소스 삭제|

### HTTP 상태 코드

- [기본 설명](https://sanghaklee.tistory.com/61)

|Code|설명|
|---|---|
|200|OK|
|201|Created|
|202|Accepted|
|204|No Content|
|400|Bad Request|
|401|Unauthorized|
|403|Forbidden|
|404|Not Found|

### 각 기능별 상황 코드 규칙

- 예외처리 상황 발생시, `status 202 (Accepted)` 와 함께 코드 응답
- 코드는 만약 ../`URL명` 에 매핑된 기능일때, { code : `URL명`_1,2,3.... } 이런식으로 명시


<br>

## Rest URL/Data Type

### 기본 Rest API 주소

|환경|주소|
|---|---|
|개발서버|http://localhost:3000/api|

### /test
> 테스트 관련

|Path|Method|Data|설명|
|---|---|---|---|
|/chk_DB|POST|테스트 데이터|Rest 통신 테스트|

### /auth
> 회원정보 관련

|Path|Method|req|res|Code|설명|
|---|---|---|---|---|
|/register|POST|{user_id, user_email, user_pw, user_name}||1:아이디 중복됨|회원가입|
|/login|POST|{user_id, user_pw}|{accessToken}|1:가입된 ID가 없음 2:비밀번호가 틀림|로그인|

