FROM python:alpine
RUN apk add --no-cache git
ARG VERSION=latest
RUN [ $VERSION = "latest" ] && pip install cookiecutter || pip install cookiecutter${VERSION+==$VERSION}
LABEL io.whalebrew.name cookiecutter
ENTRYPOINT ["cookiecutter"]
