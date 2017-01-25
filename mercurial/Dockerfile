FROM alpine
RUN apk add --no-cache --update mercurial
LABEL io.whalebrew.name hg
LABEL io.whalebrew.config.volumes '["~/.hgrc:/root/.hgrc", "~/.hgignore:/root/.hgignore", "~/.hgext:/root/.hgext"]'
ENTRYPOINT ["hg"]
