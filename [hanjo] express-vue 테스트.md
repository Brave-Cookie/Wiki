### 폴더 구조
```
ex-vue
├── backend
│   └── config (아래 참고)
└── frontend
```

### 기본 세팅

1. 터미널을 backend 폴더에서 연 후 아래 명령어로 express 관련 패키지를 설치해준다.
```
> npm install
> npm install -g nodemon
```

2. 구글 드라이브에 있는 config 폴더 (DB 접속 정보) 통째로 backend 폴더 하위로 복사한다

3. 터미널을 frontend 폴더에서 연 후 아래 명령어로 vue 관련 패키지를 설치해준다.
```
> npm install
```

### 실행하기

1. BE 서버 실행
```
# 터미널을 backend 폴더로 이동 후 일반적인 실행은 
> npm start

# or 아래 명령어로 실행하면 수정사항이 바로 반영됨
> nodemon www
```

2. FE 서버 실행
```
# 터미널을 frontend 폴더로 이동 후
> npm run serve
```

3. 주소창에 `localhost:8080`으로 접속

4. Rest API 통신 되는지 확인