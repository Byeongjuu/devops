# 7주차
여러 컨테이너를 한번에 실행하고 관리하는 Docker compose를 배움. 방명록 웹 앱과 Redis를 연결하고, Web컨테이너를 여러개로 늘리는 방법을 배움.

# Docker Compose와 데이터 관리
Docker compose는 compose.yaml 파일에 여러 서비스의 이미지, 포트, 환경 변수, 볼륨 등을 적어 한번에 관리하는 도구이다.

기존 방명록은 앱 메모리에 글을 저장하고 재시작하면 내용이 사라졌지만, Redis를 별도 컨테이너로 연결하면 Web만 재시작해도 데이터가 남는다.
또 볼륨을 사용하면 컨테이너를 삭제하고 다시 생성해도 저장된 데이터를 유지할 수 있다.

# 주요 명령어
```
docker compose up -d : 여러 서비스 실행 
docker compose p : 컨테이너 상태 확인 
docker compose logs -f web :Web 로그 확인 
docker compose restart web : Web 서비스 재시작 
docker compose down : 컨테이너와 네트워크 정리 
docker compose down -v :볼륨까지 삭제
docker compose config -q :설정 파일 검사 
```

# Scale과 nginx
```bash
docker compose up -d --scale web=3
```
이 명령어로 Web 컨테이너를 3개 실행하도록 지정할 수 있다. 하지만 Web 3개가 모두 호스트의 8080 포트를 사용하려 하면 포트 충돌이 난다.
nginx를 앞에 두어 8080 포트로 들어온 요청을 web3 개에 나눠주는 구조로 해결했다.

web컨테이너 하나를 수동을 정지해도 남은 두개가 요청을 처리할 수 있지만, 중지된 컨테이너가 저절로 3개로 복구되지 않는다.
restart: unless-stopped는 수동으로 중지한 컨테이너를 자동으로 다시 실행하지 않기 때문이다.