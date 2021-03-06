# Flask 실행법

### 파이썬 백엔드 Rest API 서버 실행


<br>

### 초기 세팅

1. `backend_flask` 폴더에서 터미널 오픈

2. 가상환경 생성
```
> python -m venv .venv
```

3. 가상환경 실행
> 터미널에 `(.venv)`가 추가되어야 정상 실행된 것.
```
> .venv/Scripts/activate
```

4. 관련 모듈 설치
> requirements 문서를 참조하여 한번에 설치.
```
> pip install -r requirements.txt
```

5. Flask 실행
```
> python app.py
```

6. 가상환경 종료
```
> deactivate
```




### 설치 모듈 리스트 추출

1. 가상환경 실행

2. 명령어 실행
```
> pip freeze > requirements.txt
```

3. `backend_flask` 폴더 하위에 txt 파일 생성


### 주의사항

- 가상환경은 자신의 컴퓨터에 맞춰진 것으로, `.gitignore`로 깃허브에 업로드 X
- 파이썬 모듈을 설치(pip install)할때 항상 가상환경 내에서 설치
