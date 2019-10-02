FROM alpine AS download
RUN apk add --no-cache --update curl bash openssl
ARG VERSION
RUN curl https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash -- /dev/stdin ${VERSION+--version ${VERSION}}

FROM alpine
COPY --from=download /usr/local/bin/helm /usr/local/bin/helm
LABEL io.whalebrew.name helm
LABEL io.whalebrew.config.volumes '["~/.helm:/.helm","~/.kube:/.kube"]'
ENTRYPOINT ["helm"]
