FROM alpine
ENV VERSION 0.40.3
ADD https://github.com/gohugoio/hugo/releases/download/v${VERSION}/hugo_${VERSION}_Linux-64bit.tar.gz  /tmp/hugo.tar.gz
RUN tar -xzvf /tmp/hugo.tar.gz -C /tmp && cp /tmp/hugo /bin/hugo && chmod +x /bin/hugo && rm -r /tmp/hugo*
ENTRYPOINT ["hugo"]
