FROM alpine:latest

RUN apk update &&\
    apk add openssh-client bash
RUN adduser -D -s /bin/bash -h /home/ssh ssh

USER ssh
WORKDIR /home/ssh

LABEL io.whalebrew.name ssh
LABEL io.whalebrew.config.volumes '["~/.ssh:/home/ssh/.ssh:ro"]'

ENTRYPOINT ["ssh"]
