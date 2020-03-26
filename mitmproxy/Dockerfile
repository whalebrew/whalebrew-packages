FROM python:3.8-alpine

ENV LANG=en_US.UTF-8
LABEL io.whalebrew.config.ports '["8080:8080"]'
LABEL io.whalebrew.config.volumes '["~/.mitmproxy:/root/.mitmproxy"]'
COPY requirements.txt /tmp/requirements.txt

# add our user first to make sure the ID get assigned consistently,
# regardless of whatever dependencies get added
RUN apk add --no-cache \
		su-exec \
		git \
		g++ \
		libffi \
		libffi-dev \
		libjpeg-turbo \
		libjpeg-turbo-dev \
		libstdc++ \
		libxml2 \
		libxml2-dev \
		libxslt \
		libxslt-dev \
		openssl \
		openssl-dev \
		python3-dev \
		zlib \
		zlib-dev \
    && python3 -m ensurepip \
    && LDFLAGS=-L/lib pip3 install -r /tmp/requirements.txt \
    && apk del --purge \
        git \
        g++ \
        libffi-dev \
        libjpeg-turbo-dev \
        libxml2-dev \
        libxslt-dev \
        openssl-dev \
        python3-dev \
        zlib-dev \
    && rm /tmp/requirements.txt \
    && rm -rf ~/.cache/pip
ENTRYPOINT ["mitmproxy"]
EXPOSE 8080 8080
