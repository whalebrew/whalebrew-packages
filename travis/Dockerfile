FROM ruby:2.4-alpine

LABEL io.whalebrew.name travis
LABEL io.whalebrew.config.volumes '["~/.travis:/.travis"]'

ENV TRAVIS_VERSION 1.8.9

RUN set -x && \
    apk --update add --no-cache --virtual deps build-base && \
    apk add git && \
    gem install travis -v $TRAVIS_VERSION --no-ri --no-rdoc && \
    apk del deps

ENTRYPOINT ["travis"]
