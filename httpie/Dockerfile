FROM python:3-alpine
ARG VERSION
RUN pip install httpie${VERSION+==$VERSION}
RUN mkdir /.httpie && echo "{}" > /.httpie/config.json
ENTRYPOINT ["http"]
