FROM golang:alpine AS builder
WORKDIR /app
COPY . .
RUN go build -ldflags="-s -w" -tags netgo -trimpath -o Z-BingAI-Q main.go

FROM alpine
WORKDIR /app
COPY --from=builder /app/Z-BingAI-Q .

EXPOSE 8080
CMD ["/app/Z-BingAI-Q"]
