# Dockerfile
FROM golang:1.22

WORKDIR /app

# Copy module files and main.go
COPY go.mod go.sum ./
COPY main.go .

# Download dependencies
RUN go mod tidy

# Build binary
RUN go build -o dispatch

CMD ["./dispatch"]
