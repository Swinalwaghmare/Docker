FROM ubuntu:latest

WORKDIR /app

COPY requirements.txt .

RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip3 install --no-cache-dir -r requirements.txt &&\
    apt-get clean &&\
    rm -rf /var/lib/apt/lists/*

COPY . .

EXPOSE 5000

ENTRYPOINT ["python3"]

CMD ["app.py"]
