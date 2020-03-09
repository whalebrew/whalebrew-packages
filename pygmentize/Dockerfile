FROM python:3-alpine
ARG VERSION=2.6.1
RUN pip install pygments${VERSION+==$VERSION}
ENTRYPOINT ["pygmentize"]
