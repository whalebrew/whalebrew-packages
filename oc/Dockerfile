FROM alpine AS download
RUN apk add --no-cache --update curl && \
    curl -LO https://mirror.openshift.com/pub/openshift-v4/clients/ocp/stable/openshift-client-linux.tar.gz && \
    tar xvzf openshift-client-linux.tar.gz && \
    chmod +x oc

FROM alpine
COPY --from=download /oc /usr/local/bin/oc
COPY --from=download /kubectl /usr/local/bin/kubectl
LABEL io.whalebrew.name oc
LABEL io.whalebrew.config.volumes '["~/.kube:/.kube"]'
ENTRYPOINT ["oc"]
