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

## 기본 Rest API 주소

|환경|주소|
|---|---|
|개발서버|http://localhost:3000/api|

<br>

## 테스트
> 테스트를 수행하는 기능 어쩌구

|Path|Type|설명|
|---|---|---|
|/DB_chk|String|Rest 통신 테스트|