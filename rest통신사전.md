# Rest API 통신 사전

### 프론트 - 백 협업할때 형식 정해놓기

<br>

## Restful 규칙
> [자세한 규칙](https://one-it.tistory.com/entry/RESTful-API-%EC%84%A4%EA%B3%84-%EA%B7%9C%EC%B9%99)

|HTTP Method|설명|
|---|---|
|GET|조회(받겠다)|
|POST|리소스 생성(보내겠다)|
|PUT|리소스 전체 갱신(넣겠다)|
|PATCH|리소스 부분 갱신(붙이겠다)|
|DELETE|리소스 삭제|

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

|Path|Method|Data|설명|
|---|---|---|---|
|/register|POST|user_id, user_pw, user_name, user_email|회원정보 등록|
|/login|GET? POST? -> 잘 모르겠어요..|???|회원이 등록되었는지 확인 후 accessToken |


