# Docker 사용법

### Docker로 편하게 개발환경 구축하기

<br>

## Dockerfile 빌드

> Frontend는 로컬에서 작업

### 빌드 전 주의사항

- 열려있는 서버 포트는 모두 닫아준다
- Docker Desktop에서 Containers/Images를 모두 삭제한다.


### Express Docker 빌드

1. `backend` 폴더에서 터미널 오픈

2. 도커 이미지 생성 (아래 명령어 실행)

```
> docker build . -t backend_express
```

3. 해당 이미지로 도커 컨테이너 생성

```
> docker run -d --name con_backend_express -p 3000:3000 -v ${PWD}:/myfolder/ backend_express
```

### Flask Docker 빌드

1. `backend_flask` 폴더에서 터미널 오픈

2. 도커 이미지 생성 (아래 명령어 실행)

```
> docker build . -t backend_flask
```

3. 해당 이미지로 도커 컨테이너 생성

```
> docker run -d --name con_backend_flask -p 5000:5000 -v ${PWD}:/myfolder/ backend_flask
```

<br>

## 빌드 후 관리

### Docker Desktop

- Docker Desktop -> Containers 에서 각 백엔드에 해당하는 터미널을 확인 가능
- Containers에서 서버를 껐다 켰다 할 수 있음. 

### 코드변경 / Pull

- 데이터가 바인딩되어있어 코드가 변경되면 수정사항이 바로 반영됨
- 서버(컨테이너) 켜진 상태에서 Git pull해도 바로 반영됨

### 실행이 안될 때

- Express의 경우 모듈이 추가되었을 수 있으므로, 서버를 꺼두고 로컬에서 npm install 후 다시 킨다.
- 그래도 안되면 Docker Desktop에서 모든 객체를 삭제하고 재빌드.
- Flask의 경우엔 모듈을 추가하는 사람이 추가하기 전 미리 말해야함. (기존 이미지 삭제 -> requirements.txt 변경 -> 재빌드 )

