# ---------------------------------------------------------------
# 학생 과제: 아래 각 줄이 무엇을 하는지 주석으로 설명을 달아보세요.
# ---------------------------------------------------------------

FROM python:3.12-slim
#Python3.12.의 경량 이미지를 기반 이미지로 사용

WORKDIR /app
#컨테이너 내부 작업 디렉터리를 /app으로 설정

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
#의존성 목록 파일을 컨테이너의 /app 디렉터리에 복사, requiremnet.txt에 정의된 python 패키지를 설치

COPY . .
#현재 프로젝트의 나머지 파일들을 컨테이너로 복사

RUN useradd -m appuser
USER appuser
#보안을 위해 일반 사용자 appuser를 생성, 이후 명령과 프로그램을 appuser 권한으로 실행


ENV APP_TITLE="병주의 방명록" \
    THEME_COLOR="#0054A6"
#방명록 제목과 테마 색상을 환경 변수로 설정

EXPOSE 5000
#애플리케이션이 사용하는 5000번 포트를 문서화

CMD ["python", "app.py"]
#컨테이너가 시작될 때 app.py를 python으로 실행
