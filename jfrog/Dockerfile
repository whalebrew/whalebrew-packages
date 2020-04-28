ARG VERSION=1.35.3

FROM docker.bintray.io/jfrog/jfrog-cli-go:${VERSION}
USER 1000:1000
LABEL io.whalebrew.config.volumes '["$HOME/.jfrog:$HOME/.jfrog"]'
LABEL io.whalebrew.config.environment '["HOME"]'
ENTRYPOINT ["jfrog"]
