FROM golang:1.22

WORKDIR /app

RUN go mod init main
RUN go mod tidy

COPY ./src /app

RUN go build

ENV CGO_ENABLED=0
ENV GOOS=linux
ENV GOARCH=amd64

EXPOSE 8080

CMD ["go", "run", "main.go"]