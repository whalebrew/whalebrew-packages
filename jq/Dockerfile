FROM alpine as build
ARG VERSION=1.6
RUN wget -O /usr/local/bin/jq https://github.com/stedolan/jq/releases/download/jq-${VERSION}/jq-linux64 && \
    chmod +x /usr/local/bin/jq
FROM scratch
COPY --from=build /usr/local/bin/jq /usr/local/bin/jq
ENTRYPOINT ["jq"]
