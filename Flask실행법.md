# Flask 서버 가상환경 설정

### 의존성 문제 발생 방지를 위해 파이썬 가상환경 사용


<br>

### 가상환경 .venv 사용법

1. ` backend_flask` 폴더에서 터미널 오픈

2. 가상환경 생성
```
> python -m venv .venv
```

3. 가상환경 실행
```
> .venv/Scripts/activate
```
> 터미널에 `(.venv)`가 추가되어야 정상 실행된 것.

4. Flask 실행
```
> python app.py
```

### 주의사항

- 가상환경은 자신의 컴퓨터에 맞춰진 것으로, `.gitignore`로 깃허브에 업로드 X
- 파이썬 모듈을 설치(pip install)할때 항상 가상환경 내에서 설치
