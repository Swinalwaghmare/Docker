FROM ubuntu:latest

WORKDIR /app

COPY requirements.txt .

RUN apt-get update && apt-get install python3 python3-pip && pip install -r requirements.txt

EXPOSE "5000"

ENTRYPOINT ["python3"]

CMD ["app.py"]
