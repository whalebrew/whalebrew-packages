FROM google/cloud-sdk:latest

LABEL io.whalebrew.config.volumes '["~/.config:/config"]'
LABEL io.whalebrew.config.environment '["K8S_SERVER", "K8S_TOKEN"]'

COPY entrypoint.sh /usr/local/bin/entrypoint.sh

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
