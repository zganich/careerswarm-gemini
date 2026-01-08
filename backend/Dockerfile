FROM mcr.microsoft.com/playwright/python:v1.41.0-jammy

WORKDIR /app

RUN apt-get update && apt-get install -y     python3-pip python3-cffi python3-brotli libpango-1.0-0 libpangoft2-1.0-0     libharfbuzz-subset0 libjpeg-dev libopenjp2-7-dev libffi-dev     && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
