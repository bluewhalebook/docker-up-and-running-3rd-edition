# Build container
FROM docker.io/golang:alpine as builder

RUN apk update && \
    apk add git && \
    CGO_ENABLED=0 go install -a -ldflags '-s' github.com/adriaandejonge/helloworld@latest

# Production container
FROM scratch

COPY --from=builder /go/bin/helloworld /helloworld
EXPOSE 8080
CMD ["/helloworld"]
