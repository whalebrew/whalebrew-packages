ARG VERSION
FROM sridca/neuron@sha256:${VERSION}
LABEL io.whalebrew.config.ports '["8080:8080","1440:1440"]'
LABEL io.whalebrew.config.volumes_from_args '["-d", "-o", "--output-dir"]'
LABEL io.whalebrew.config.working_dir '$PWD'

ENTRYPOINT ["neuron"]
