FROM alpine
RUN apk add --no-cache python
ADD https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py /speedtest
ENTRYPOINT ["python","/speedtest"]
