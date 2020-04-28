FROM alpine AS download
ARG VERSION
RUN apk add --no-cache --update curl

RUN ! [ -z "${VERSION}" ] || export VERSION=$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt); \
curl -LO https://storage.googleapis.com/kubernetes-release/release/$VERSION/bin/linux/amd64/kubectl && \
chmod +x kubectl

FROM alpine
COPY --from=download /kubectl /usr/local/bin/kubectl
LABEL io.whalebrew.name kubectl
LABEL io.whalebrew.config.volumes '["~/.kube:/.kube"]'
ENTRYPOINT ["kubectl"]
