FROM python:3-alpine
ARG VERSION=2.0.0
RUN pip install httpie${VERSION+==$VERSION}
RUN mkdir /.httpie && echo "{}" > /.httpie/config.json
ENTRYPOINT ["http"]
