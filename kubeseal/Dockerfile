FROM alpine as download
RUN apk add --no-cache curl
ARG VERSION
ENV GITHUB_REPO=bitnami-labs/sealed-secrets

RUN mkdir /download
WORKDIR /download

# kubeseal changed its packaging method starting with v0.17
RUN ! [ -z "${VERSION}" ] || export VERSION=$(curl -w%{url_effective} -Ls -o /dev/null https://github.com/${GITHUB_REPO}/releases/latest | grep -oE "[^/]+$"); \
    curl -L -s -vvv https://github.com/${GITHUB_REPO}/releases/download/${VERSION}/kubeseal-${VERSION#v}-linux-amd64.tar.gz | gunzip | tar xv || \
    curl -L -s -vvv -o kubeseal https://github.com/bitnami-labs/sealed-secrets/releases/download/${VERSION}/kubeseal-linux-amd64 && chmod +x kubeseal

FROM alpine

COPY --from=download /download/kubeseal /bin/kubeseal
LABEL io.whalebrew.config.volumes '["~/.kube:/.kube"]'
ENTRYPOINT ["/bin/kubeseal"]
