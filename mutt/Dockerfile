FROM alpine
RUN apk add --no-cache mutt vim
LABEL io.whalebrew.config.environment '["TERM"]'
LABEL io.whalebrew.config.volumes '["~/.mutt:/root/.mutt"]'
ENTRYPOINT ["mutt"]
