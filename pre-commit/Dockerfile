FROM python:alpine
RUN apk add --no-cache git
ARG VERSION
RUN pip install pre-commit${VERSION+==$VERSION}
LABEL io.whalebrew.config.environment '["SKIP"]'
LABEL io.whalebrew.config.keep_container_user 'true'
LABEL io.whalebrew.name pre-commit
ENTRYPOINT ["pre-commit"]
