FROM python:3-alpine
ARG VERSION=0.9.0
RUN pip install proselint${VERSION+==$VERSION}
ENTRYPOINT ["proselint"]
