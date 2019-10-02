FROM python:3-alpine
RUN apk add --no-cache ffmpeg
ARG VERSION
RUN pip install youtube-dl${VERSION+==$VERSION}
ENTRYPOINT ["youtube-dl"]
