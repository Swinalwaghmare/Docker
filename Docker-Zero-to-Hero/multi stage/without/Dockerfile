FROM ubuntu:latest

WORKDIR /app

RUN apt-get update && apt-get install -y golang-go

ENV GO111MODULE=off

COPY . .

RUN CGO_ENABLE=0 go build -o /app . 

ENTRYPOINT ["/app"]