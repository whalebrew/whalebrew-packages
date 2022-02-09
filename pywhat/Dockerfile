# syntax=docker/dockerfile:1
FROM python:3-alpine

LABEL io.whalebrew.name pywhat
LABEL io.whalebrew.required_version >0.3.0

ARG VERSION=3.2.0

RUN pip install pywhat${VERSION+==$VERSION}
ENTRYPOINT ["pywhat"]
