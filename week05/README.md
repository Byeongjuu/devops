## 5주차 
## 배운 내용
- Docker와 컨테이너의 개념
- 가상 머신과 컨테이너의 차이
- Docker를 이용한 nginx 웹 서버 실행

## Docker
- 프로그램을 실행하는 데 필요한 환경을 이미지로 만들어 사용할 수 있는 도구
- 이미지는 프로그램 실행에 필요한 파일과 설정을 묶어놓은 틀이고, 컨테이너는 이미지를 실제로 실행한 것
- 가상머신과 달리 컨테이너는 호스트 운영체제의 커널을 공유한다.

## 주요 명령어
```
docker run -d -p 8080:80 --name wdb nginx
-d는 백그라운드 실행, -p는 컴퓨터의 포트와 컨테이너의 포트를 연결하는 옵션
docker run
docker ps
docker stop
docker rm
```
## 깃헙 이슈
- 프로젝트에서 해야 할 작업이나 문제들을 기록하고 관리하는 기능
- Docker 실습 내용을 이슈로 등록하고 브랜치를 생성하고 작업한 뒤 풀 리퀘스트와 머지를 진행하는 과정을 배움.














## 수업 중 과제
<h1>Welcome to nginx1</h1>
<h1>Welcome to nginx2</h1>
<h1>Welcome to nginx3</h1>
