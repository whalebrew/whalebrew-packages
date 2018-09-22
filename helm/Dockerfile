FROM alpine
RUN apk add --no-cache --update curl bash openssl && \
cd /usr/local/bin && \
curl https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash && \
chmod +x helm && \
apk del curl bash openssl
LABEL io.whalebrew.name helm
LABEL io.whalebrew.config.volumes '["~/.helm:/.helm","~/.kube:/.kube"]'
ENTRYPOINT ["helm"]
