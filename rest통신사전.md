# Rest API 통신 사전

### 프론트 - 백 협업할때 형식 정해놓기

<br>

## Rest 통신 규칙

### Restful HTTP Method

- [Rest 통신 기본 개념](https://one-it.tistory.com/entry/RESTful-API-%EC%84%A4%EA%B3%84-%EA%B7%9C%EC%B9%99)
- [POST와 GET의 차이](https://im-developer.tistory.com/166)
- [URI 규칙](https://devuna.tistory.com/79)

| HTTP Method | 설명                       |
| ----------- | -------------------------- |
| GET         | 조회(받겠다)               |
| POST        | 리소스 생성(보내겠다)      |
| PUT         | 리소스 전체 갱신(넣겠다)   |
| PATCH       | 리소스 부분 갱신(붙이겠다) |
| DELETE      | 리소스 삭제                |

### HTTP 상태 코드

- [기본 설명](https://sanghaklee.tistory.com/61)

| Code | 설명         |
| ---- | ------------ |
| 200  | OK           |
| 201  | Created      |
| 202  | Accepted     |
| 204  | No Content   |
| 400  | Bad Request  |
| 401  | Unauthorized |
| 403  | Forbidden    |
| 404  | Not Found    |

### 각 기능별 상황 코드 규칙

- 예외처리 상황 발생시, `status 202 (Accepted)` 와 함께 코드 응답
- 예외처리 코드는 반드시 통신 사전에 기재
- 코드는 만약 ../`URL명` 에 매핑된 기능일때, { code : `URL명`\_1,2,3.... } 이런식으로 명시

```
ex) { code : login_1 }
```

<br>

## React Frontend 주소

### 기본 도메인
> 데모 버전까지만 구현하므로 8080포트로 개발모드 구동

| 환경     | 주소                      |
| -------- | ------------------------- |
| 개발서버 | `https://localhost:8080` |
| 배포서버 | `https://3.36.71.108:8080` |
| 도메인버전 | `https://ec2-3-36-71-108.ap-northeast-2.compute.amazonaws.com:8080` |

<br>

## Express Rest API 주소

### 기본 Domain

| 환경     | 주소                      |
| -------- | ------------------------- |
| 개발서버 | `https://localhost:3000/api` |
| 배포서버 | `https://13.124.239.189:3000/api` |

### /test

> 테스트 관련

| Path                          | Method | req | res                   | Code | 설명              |
| ----------------------------- | ------ | --- | --------------------- | ---- | ----------------- |
|/chk_DB|POST||{test DB}||api 서버 응답 테스트|

### /auth

> 인증 관련

| Path             | Method | req                                       | res           | Code                                     | 설명                               |
| ---------------- | ------ | ----------------------------------------- | ------------- | ---------------------------------------- | ---------------------------------- |
| /register        | POST   | {user_id, user_email, user_pw, user_name} |               | 1:아이디 중복됨                          | 회원가입                           |
| /login           | POST   | {user_id, user_pw}                        | {accessToken} | 1:가입된 ID가 없음 <br>2:비밀번호가 틀림 | 로그인                             |
| /createRoom  | POST    |  {room_code, meeting_name}      |               |                                          | 회의방 임시정보 저장        |
| /check/:roomCode | GET    |                                           |   { meeting_name }   |checkCode_1 : 방존재 X                                          | 참여코드 유효성검사 |

### /project

> 프로젝트 관련

| Path                      | Method | req                         | res                                              | Code                 | 설명                               |
| ------------------------- | ------ | --------------------------- | ------------------------------------------------ | -------------------- | ---------------------------------- |
| /create                   | POST   | {user_id, project_name}     |                                                  |                      | 프로젝트 생성                      |
| /list/:user_id            | GET    |                             | {list : {project_id,project_name,count,date}}               |                      | 사용자가 소유한 프로젝트 추출      |
| /issue/create             | POST   | {project_id, issue_content} |                                                  |                      | 이슈등록                           |
| /issue/list/:project_id   | GET    |                             | {list : {issue_content}}                         |                      | 프로젝트에 해당하는 이슈 추출      |
| /member/search/:user_name | GET    |                             | {list : {user_id}}                               | 1.해당 사용자가 없음 | 사용자 이름에 해당하는 아이디 추출 |
| /member/add               | POST   | {project_id, user_id}       |                                                  | 1.이미 추가한 사용자 | 참여자등록                         |
| /member/list/:project_id  | GET    |                             | {list: {user_id}}                                |                      | 프로젝트에 해당하는 사용자 추출    |
| /log/list/:project_id     | GET    |                             | {list: {meeting_id, meeting_date, meeting_name}} |                      | 프로젝트에 해당하는 회의록 추출    |

### /meetingLog

> 회의록 관련

| Path                           | Method | req | res                                                 | Code | 설명                                |
| ------------------------------ | ------ | --- | --------------------------------------------------- | ---- | ----------------------------------- |
| /log/fetch/:meeing_id          | GET    |     | {list : {user_id, log_time, log_feeling, log_text}} |      | 회의록 내용 가져오기                |
| /log/fetch/:meeing_id/:feeling | GET    |     | {list : {user_id, log_time, log_feeling, log_text}} |      | 감정 필터링 된 회의록 내용 가져오기 |
| /log/rank/:meeting_id/:feeling | GET    |     | firstrank ,total_rank{list: {user_id}}, count                             |      | 보낸감정중 가장 많이 나온사람, 참여도 순위, 감정별발언1등의발언횟수        |
| /log/avgFeeling/:meeing_id | GET    |     |avg:{time,emotion} |      | 회의 평균 감정 리스트  |

<br>

## Flask Rest API 주소

### 기본 Domain

| 환경     | 주소                      |
| -------- | ------------------------- |
| 개발서버 | `https://localhost:5000/api` |
| 배포서버 | `https://13.124.239.189:5000/api` |

### /test

> 테스트용

| Path                          | Method | req | res                   | Code | 설명              |
| ----------------------------- | ------ | --- | --------------------- | ---- | ----------------- |
|/|POST||||api 서버 응답 테스트|


### /log

> 회의록 관련

| Path                          | Method | req | res                   | Code | 설명              |
| ----------------------------- | ------ | --- | --------------------- | ---- | ----------------- |
| /wordcloud/:meeing_id     | GET    |     | {list :(word,count)}  |      | 단어빈도수 리스트 |
| /summary/:meeting_id      | GET    |     | summary_text          |      | 회의록요약        |
| /feelingCount/:meeting_id | GET    |     | list:{'feeling':횟수} |      | 감정빈도수        |

<br>
