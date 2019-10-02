FROM python:3-alpine
ARG VERSION
RUN pip install proselint${VERSION+==$VERSION}
ENTRYPOINT ["proselint"]
