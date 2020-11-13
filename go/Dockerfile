FROM golang:alpine AS builder


RUN apk update && apk add --no-cache git
WORKDIR $GOPATH/src/hello
COPY . .
RUN go get -d -v
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 \
    go build -a -tags netgo -ldflags '-w' -o hello hello.go

FROM scratch
COPY --from=builder /go/src/hello/hello /go/bin/hello

EXPOSE 8080

ENTRYPOINT ["/go/bin/hello"]
