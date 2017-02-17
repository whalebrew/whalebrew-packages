FROM hashicorp/terraform:latest

## Adding in case we need Terraform to call them.
RUN apk --update upgrade && \
    apk add \
        py-pip \ 
        python-dev \ 
        gcc \ 
        musl-dev \ 
        libffi-dev \ 
        openssl-dev \ 
        ca-certificates \ 
        sudo \ 
        openssl

RUN pip install \
        awscli \
        ansible && \
    rm -f /var/cache/apk/*.tar.gz

## Make sure we run as a non-privileged user
RUN adduser -g "Terraform User" -D -s /usr/sbin/nologin terraform
USER terraform

CMD ["-version"]