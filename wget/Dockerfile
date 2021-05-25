FROM alpine
RUN apk add --no-cache ca-certificates openssl wget dumb-init
ENTRYPOINT ["/usr/bin/dumb-init", "/usr/bin/wget"]
