FROM python:3.8-alpine
ARG VERSION=2.9.2
ARG JQ_VERSION=1.6
RUN wget -O /usr/local/bin/jq https://github.com/stedolan/jq/releases/download/jq-${JQ_VERSION}/jq-linux64 && \
    chmod +x /usr/local/bin/jq
RUN pip install yq${VERSION+==$VERSION}
ENTRYPOINT ["yq"]
