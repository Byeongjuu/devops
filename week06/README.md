#6주차
## 배운 내용
- Dockerfile을 이용하여 직접 Docker 이미지를 만드는 방법을 배움.
- 이미지를 만들어 도커 허브에 업로드 함.
- Dockerfile의 캐시가 어떻게 작동하는지 알아보기 위해 이미지를 다시 빌드하고, 코드를 수정하고 다시 빌드함.

## Dockerfile
- Dockerfile은 Docker이미지를 만들 때 필요한 명령어들은 순서대로 작성한 파일.

## 주요 명령어
```
FROM
WORKDIR
COPY
RUN
ENV
EXPOSE
CMD
```
- dockerfile은 위 명령어들을 순서대로 작성하여 이미지를 만드는 파일이다.
- RUN은 이미지 빌드 과정에서 실행되고 CMD는 컨테이너 시작 시 실행된다.

## 빌드 캐시 
```
docker build -t guestbook:v1.1 .
```
- 아무것도 수정하지 않고 다시 빌드하면 이전 빌드 결과를 재사용하기 때문에 같은 작업을 재수행하지 않는다.
- 좋지 않은 Dockerfile은 COPY . . 로 전체 파일을 복사한 뒤 RUN pip install을 실행한다. 이 경우 app.py만 수정해도 라이브러리를 다시 설치할 수 있다.
- 좋은 Dockerfile은 requirements.txt를 먼저 복사하고 라이브러리를 설치한 뒤 나머지 코드를 복사한다.
