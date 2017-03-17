FROM python:alpine
RUN pip install awslogs
LABEL io.whalebrew.name awslogs
LABEL io.whalebrew.config.environment '["AWS_ACCESS_KEY_ID", "AWS_SECRET_ACCESS_KEY", "AWS_DEFAULT_REGION"]'
LABEL io.whalebrew.config.volumes '["~/.aws:/.aws"]'
ENTRYPOINT ["awslogs"]
