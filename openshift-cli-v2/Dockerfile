FROM ruby:2.1-alpine
RUN apk add --no-cache git
RUN gem install rhc
LABEL io.whalebrew.name rhc
LABEL io.whalebrew.config.volumes '["~/.openshift:/root/.openshift","~/.ssh:/root/.ssh"]'
ENTRYPOINT ["rhc"]