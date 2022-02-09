FROM alpine:latest

ARG VERSION=5.3.0

RUN apk --update upgrade && \
    apk add \
        py3-pip \
        python3-dev \
        gcc \
        rust \
        cargo \
        musl-dev \
        libffi-dev \
        openssl-dev \
        ca-certificates \
        sudo \
        openssl

## Adding boto and boto3 for AWS modules.  This can obviously be expanded as needed
RUN pip install --no-cache-dir \
        pycparser==2.13 \
        ansible${VERSION+==$VERSION} \
        boto \
        boto3

RUN adduser -g "Ansible User" -D -s /usr/sbin/nologin ansible
ENTRYPOINT ["ansible-playbook"]
CMD ["--version"]