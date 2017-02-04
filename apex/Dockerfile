FROM alpine

ARG VERSION=v0.12.0
RUN apk add --no-cache curl \
    && curl https://raw.githubusercontent.com/apex/apex/${VERSION}/install.sh | sh

ENTRYPOINT ["apex"]