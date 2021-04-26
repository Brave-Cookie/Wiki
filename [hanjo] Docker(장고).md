### Docker 시작

- [Docker 란?](https://www.youtube.com/watch?v=tPjpcsgxgWc)
- [Docker(windows) 설치 링크](https://hub.docker.com/editions/community/docker-ce-desktop-windows/)
- [Docker 설치 가이드 블로그](https://goddaehee.tistory.com/251)

### Docker로 개발환경 구축
> 아래는 장고일 경우였고 node.js 환경에 맞춰 변경예정

1. 프로젝트 폴더에서 터미널 실행
2. 아래 명령어 실행
```python
# 이미지 빌드
> docker build . -t '이미지 이름'

# 이미지 실행 -> 컨테이너 생성
> docker run --name '컨테이너 이름' -p 8000:8000 -v ${PWD}:/myfolder/ '이미지 이름'
```
3. 컨테이너까지 잘 저장됐다면 브라우저에서 `localhost:8000`으로 접속 후 개발! (수정 사항 실시간 반영됨)
4. 컨테이너 조작
```python
# 컨테이너 중지
> docker stop '컨테이너 이름'

# 컨테이너 시작
> docker start '컨테이너 이름'

# 컨테이너 재시작
> docker restart '컨테이너 이름'
```