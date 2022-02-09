FROM alpine AS download
ARG VERSION

ENV GITHUB_REPO=gohugoio/hugo

RUN apk add --no-cache curl
RUN ! [ -z "${VERSION}" ] || export VERSION=$(curl -w%{url_effective} -Ls -o /dev/null https://github.com/${GITHUB_REPO}/releases/latest | grep -oE "[^/]+$"); \
    curl -L -s https://github.com/${GITHUB_REPO}/releases/download/${VERSION}/hugo_${VERSION#v}_Linux-64bit.tar.gz  | gunzip | tar xv

FROM alpine
COPY --from=download /hugo /usr/local/bin/hugo
LABEL io.whalebrew.config.ports '["1313:1313"]'

ENTRYPOINT ["hugo"]
# force-update 2022-02-10
