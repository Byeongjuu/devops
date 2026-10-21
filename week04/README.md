# 4주차

셸 명령어를 활용한 자동화와 Git 협업, 네크워크의 기본 개념과 웹 서버 접속을 배움.

`gerp`과 `find`로 파일이나 문자열을 찾고, 파이프로 `|`로 명령어를 연결하는 방법을 배웠다.

- find . -name "*.sh" : 셸 스크립트 파일 찾기
- grep "ERROR" server.log : 로그에서 ERROR 검색
- grep "ERROR" server.log | wc -l: 오류가 기록된 줄 수 확인 
- ps aux : 실행중인 프로세스 확인
- kill PID :지정한 프로세스 종료 요청

git에서는 별도의 브랜치에서 수정한 내용을 commit push로 올리고 pull request 후 merge하는 과정을 배웠다.

# 네트워크

IP 주소는 장치를 구분하는 주소이고, 포트는 같은 컴퓨터에서 어떤 서비스에 접속할지 구분하는 번호라는 것을 배웠다.
DNS는 도메인 이름으로 IP 주소를 조회할 때 사용한다.

```bash
ip addr
ping -c 4 8.8.8.8
dig google.com
python3 -m http.server 8080
curl -I http://localhost:8080
ss -tlnp
```

Python으로 간단한 웹 서버를 만들고 localhost:8080 으로 접속하는 실습이 있었다.
같은 포트를 다른 프로그램이 이미 사용중이면 충돌이 발생하므로 포트를 바꾸거나 기존 프로세스를 종료해야 한다.