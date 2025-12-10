# ---- 1. 베이스 이미지 ----
FROM python:3.10-slim

# ---- 2. 작업 디렉토리 생성 ----
WORKDIR /app

# ---- 3. 시스템 패키지 업데이트 및 패키지 설치 ----
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# ---- 4. 필요 라이브러리 설치 ----
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# ---- 5. 앱 코드 복사 ----
COPY . /app/

# ---- 6. Gradio 외부 접속 허용 ----
EXPOSE 7860

# ---- 7. 컨테이너 실행 명령 ----
CMD ["python", "app.py"]
