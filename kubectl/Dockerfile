FROM alpine
RUN apk add --no-cache --update curl && \
VERSION=$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt) && \
cd /usr/local/bin && \
curl -LO https://storage.googleapis.com/kubernetes-release/release/$VERSION/bin/linux/amd64/kubectl && \
chmod +x kubectl && \
apk del curl
LABEL io.whalebrew.name kubectl
LABEL io.whalebrew.config.volumes '["~/.kube:/.kube"]'
ENTRYPOINT ["kubectl"]
