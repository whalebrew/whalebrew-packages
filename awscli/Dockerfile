FROM python:alpine
RUN apk add --no-cache groff less mailcap
RUN pip install awscli
LABEL io.whalebrew.name aws
LABEL io.whalebrew.config.environment '["AWS_ACCESS_KEY_ID", "AWS_SECRET_ACCESS_KEY", "AWS_DEFAULT_REGION"]'
LABEL io.whalebrew.config.volumes '["~/.aws:/root/.aws"]'
ENTRYPOINT ["aws"]
