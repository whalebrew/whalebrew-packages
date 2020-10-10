FROM python:alpine
RUN apk add --no-cache git
ARG VERSION=1.7.2
RUN pip install cookiecutter${VERSION+==$VERSION}
LABEL io.whalebrew.name cookiecutter
ENTRYPOINT ["cookiecutter"]
