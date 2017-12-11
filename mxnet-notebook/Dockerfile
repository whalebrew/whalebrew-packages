FROM mxnet/python

LABEL io.whalebrew.name mxnet-notebook
LABEL io.whalebrew.config.ports '["8888:8888"]'
LABEL io.whalebrew.config.volumes '["$HOME:/notebook/data:rw"]'
LABEL io.whalebrew.config.working_dir '/notebook'

RUN pip install jupyter matplotlib gluon
# Jupyter needs to create a sub directory in '.local', give the daemon permissions
RUN mkdir /.local && chmod 777 /.local
ENTRYPOINT ["jupyter", "notebook", "--allow-root", "--ip='0.0.0.0'"]
