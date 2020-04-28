FROM alpine as download
RUN apk add --no-cache curl
ARG VERSION
ENV GITHUB_REPO tsenart/vegeta
RUN ! [ -z "${VERSION}" ] || export VERSION=$(curl -w%{url_effective} -Ls -o /dev/null https://github.com/${GITHUB_REPO}/releases/latest | grep -oE "[^/]+$"); \
    curl -L -s https://github.com/${GITHUB_REPO}/releases/download/${VERSION}/vegeta-${VERSION#v}-linux-amd64.tar.gz | gunzip | tar xv

FROM alpine
COPY --from=download /vegeta /usr/local/bin/vegeta
ENTRYPOINT ["vegeta"]
