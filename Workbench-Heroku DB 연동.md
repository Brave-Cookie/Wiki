저번에 워크벤치에 연결했던 DB서버(AWS)는 과금문제로 사용할 수 없게 됨....

그래서 Heroku로 DB서버 새로 만들었음 -> 워크벤치에서 새로 연결해주자.

### 1. 새 커넥션 생성
![image](https://user-images.githubusercontent.com/71180414/115146057-f10f2080-a08f-11eb-9569-a54e62556bb0.png)

### 2. 쓸거 써주고 Test Connection 클릭

```
Hostname : us-cdbr-east-03.cleardb.com
Username : bfa9ba156c2149
Default Schema : heroku_84c3432edd6c39e
```

![image](https://user-images.githubusercontent.com/71180414/115146061-f53b3e00-a08f-11eb-8372-6b7b48f9de67.png)

### 3. 비번 입력 하고 저장하기 꼭 체크! (비번 개어려우니까)

```
Password : bc1ead3c
```

![image](https://user-images.githubusercontent.com/71180414/115146065-f7050180-a08f-11eb-81b6-4086e76b0179.png)



## 참고 링크

### Heroku APP에 MySQL 생성
- https://m.blog.naver.com/gofkdvjvl/222041889095