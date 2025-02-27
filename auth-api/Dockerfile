# Use Golang base image
FROM golang:1.21-alpine AS builder

# Set working directory
WORKDIR /app

# Copy files and build
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o auth-api

# Final stage
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/auth-api .

CMD ["./auth-api"]
