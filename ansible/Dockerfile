FROM alpine:latest
ARG VERSION

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

## Adding boto and boto3 for AWS modules.  This can obviously be expanded as needed
RUN pip install --no-cache-dir \
        pycparser==2.13 \ 
        ansible${VERSION+==$VERSION} \ 
        boto \ 
        boto3

RUN adduser -g "Ansible User" -D -s /usr/sbin/nologin ansible
ENTRYPOINT ["ansible-playbook"]
CMD ["--version"]