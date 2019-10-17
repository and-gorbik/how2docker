FROM golang AS builder
WORKDIR /go/src/app
COPY . .
RUN go get -d ./... && \
    CGO_ENABLED=0 GOOS=linux go build -a -ldflags '-extldflags "-static"'

FROM alpine
WORKDIR /app
COPY --from=builder /go/src/app .
CMD ["./app"]
