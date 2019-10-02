FROM python:3-alpine
ARG VERSION
RUN pip install pygments${VERSION+==$VERSION}
ENTRYPOINT ["pygmentize"]
