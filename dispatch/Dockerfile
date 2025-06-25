FROM golang:1.22

WORKDIR /app

COPY main.go .

RUN go mod init dispatch && go mod tidy
RUN go build -o dispatch

CMD ["./dispatch"]
