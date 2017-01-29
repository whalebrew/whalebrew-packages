FROM alpine
ENV VERSION 6.1.1
ADD https://github.com/tsenart/vegeta/releases/download/v${VERSION}/vegeta-v${VERSION}-linux-amd64.tar.gz /tmp/vegeta.tar.gz
RUN apk update && apk --no-cache add ca-certificates && tar -zxvf /tmp/vegeta.tar.gz -C /bin && chmod +x /bin/vegeta && rm /tmp/vegeta.tar.gz && rm -rf /var/cache/*
ENTRYPOINT ["vegeta"]
