#FROM python:3.6-alpine
FROM python:3.9-slim

RUN apt-get update && apt-get install -y \
    build-essential \
    libssl-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app
COPY requirements.txt .
RUN pip install --upgrade pip
RUN  pip3 install -r requirements.txt

COPY main.py .

CMD ["python3","-u","main.py"]

