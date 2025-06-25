# Use Go 1.23 to match go.mod requirements
FROM golang:1.23

WORKDIR /app

COPY go.mod go.sum ./
COPY main.go .

RUN go mod tidy

RUN go build -o dispatch

CMD ["./dispatch"]
