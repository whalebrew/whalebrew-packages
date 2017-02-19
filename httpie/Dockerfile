FROM python:3-alpine
RUN pip install httpie
RUN mkdir /.httpie && echo "{}" > /.httpie/config.json
ENTRYPOINT ["http"]
