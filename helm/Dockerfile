FROM alpine AS download
RUN apk add --no-cache --update curl bash openssl
ARG VERSION=3.1.1
RUN curl https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash -- /dev/stdin ${VERSION+--version v${VERSION}}

FROM alpine
RUN apk add --no-cache ca-certificates
COPY --from=download /usr/local/bin/helm /usr/local/bin/helm
LABEL io.whalebrew.name helm
LABEL io.whalebrew.config.volumes '["~/.helm:/.helm","~/.kube:/.kube","~/.cache/helm:/.cache/helm","~/.config/helm:/.config/helm"]'
ENTRYPOINT ["helm"]
