FROM alpine

ARG VERSION=0.12.1
RUN wget -O /bin/kubeseal https://github.com/bitnami-labs/sealed-secrets/releases/download/v${VERSION}/kubeseal-linux-amd64 && \
    chmod +x /bin/kubeseal
LABEL io.whalebrew.config.volumes '["~/.kube:/.kube"]'
ENTRYPOINT ["/bin/kubeseal"]
