FROM alpine:3.5
LABEL io.whalebrew.name sfn
LABEL io.whalebrew.config.working_dir /workdir
LABEL io.whalebrew.config.environment '["AWS_ACCESS_KEY_ID", "AWS_SECRET_ACCESS_KEY", "AWS_SESSION_TOKEN", "AWS_DEFAULT_REGION", "AWS_DEFAULT_PROFILE", "AWS_CONFIG_FILE"]'
LABEL io.whalebrew.config.volumes '["~/.aws:/.aws", "$PWD:/workdir"]'

RUN apk update && \
    apk --no-cache add ruby \
    build-base ruby-dev libc-dev linux-headers \
    ruby-bundler && \
    gem update --system  --no-rdoc --no-ri && \
    gem install --no-rdoc --no-ri json && \
    gem install --no-rdoc --no-ri sfn -v '>=3.0.26'
ENTRYPOINT ["/usr/bin/sfn"]
