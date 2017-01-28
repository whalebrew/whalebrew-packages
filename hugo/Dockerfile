FROM alpine
ENV VERSION 0.18.1
ADD https://github.com/spf13/hugo/releases/download/v${VERSION}/hugo_${VERSION}_Linux-64bit.tar.gz /tmp/hugo.tar.gz
RUN tar -xzvf /tmp/hugo.tar.gz -C /tmp && cp /tmp/hugo_${VERSION}_linux_amd64/hugo_${VERSION}_linux_amd64 /bin/hugo && chmod +x /bin/hugo && rm -r /tmp/hugo*
ENTRYPOINT ["hugo"]
