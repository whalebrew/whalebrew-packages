FROM python:3-alpine
RUN apk add --no-cache ffmpeg
ARG VERSION=2020.3.8
RUN pip install --no-cache-dir youtube-dl${VERSION+==$VERSION}
ENTRYPOINT ["youtube-dl"]
