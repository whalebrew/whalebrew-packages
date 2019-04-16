FROM busybox

ARG TRIDENT_VERSION="19.01.0"

RUN set -ex && \
    wget -q https://github.com/NetApp/trident/releases/download/v${TRIDENT_VERSION}/trident-installer-${TRIDENT_VERSION}.tar.gz && \
    tar xzvf trident-installer-${TRIDENT_VERSION}.tar.gz && \
    mv trident-installer/tridentctl /tridentctl && \
    chmod +x /tridentctl

RUN set -ex && \
    wget -q https://storage.googleapis.com/kubernetes-release/release/$(wget -O- -q https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && \
    mv kubectl /kubectl && \
    chmod +x /kubectl && \
    /kubectl version --client

FROM debian

LABEL io.whalebrew.name tridentctl
LABEL io.whalebrew.config.environment '["KUBECONFIG","HOME"]'
LABEL io.whalebrew.config.volumes '["~/.kube:$HOME/.kube:ro","~/.minikube:$HOME/.minikube:ro"]'

COPY --from=0 /tridentctl /usr/local/bin/tridentctl
COPY --from=0 /kubectl /usr/local/bin/kubectl
ENV HOME /nobody
RUN set -x && \
    mkdir -p "$HOME" && \
    chown nobody:nogroup "$HOME"
USER nobody

ENTRYPOINT ["tridentctl"]
