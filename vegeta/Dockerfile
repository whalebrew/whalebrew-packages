FROM alpine as download
RUN apk add --no-cache curl
ARG VERSION
ENV GITHUB_REPO tsenart/vegeta
# in vegeta 12.8.4, the assets path changed. try both:
# https://github.com/tsenart/vegeta/releases/tag/v12.8.4
RUN ! [ -z "${VERSION}" ] || export VERSION=$(curl -w%{url_effective} -Ls -o /dev/null https://github.com/${GITHUB_REPO}/releases/latest | grep -oE "[^/]+$"); \
    curl -L -s -vvv https://github.com/${GITHUB_REPO}/releases/download/${VERSION}/vegeta-${VERSION#v}-linux-amd64.tar.gz | gunzip | tar xv || \
    curl -L -s -vvv https://github.com/${GITHUB_REPO}/releases/download/${VERSION}/vegeta_${VERSION#v}_linux_amd64.tar.gz | gunzip | tar xv

FROM alpine
COPY --from=download /vegeta /usr/local/bin/vegeta
ENTRYPOINT ["vegeta"]
