FROM debian
RUN apt-get update -qq && apt-get install -qy curl && \
    curl https://hyper-install.s3.amazonaws.com/hyper-linux-x86_64.tar.gz | tar -xvzC /usr/bin && \
    chmod +x /usr/bin/hyper && \
    apt-get remove --purge -y curl $(apt-mark showauto) && \
    rm -rf /var/lib/apt/lists/*
LABEL io.whalebrew.config.volumes '["~/.hyper:/.hyper"]'
ENTRYPOINT ["/usr/bin/hyper"]
