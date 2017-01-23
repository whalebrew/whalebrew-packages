FROM python:3-alpine
RUN apk add --no-cache ffmpeg
RUN pip install youtube-dl
ENTRYPOINT ["youtube-dl"]
