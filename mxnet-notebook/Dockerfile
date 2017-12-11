FROM mxnet/python
RUN pip install jupyter matplotlib gluon
LABEL io.whalebrew.name mxnet-notebook
LABEL io.whalebrew.config.ports '["8888:8888"]'
LABEL io.whalebrew.config.volumes '["~/:/root/dev:rw"]'
ENTRYPOINT ["jupyter", "notebook", "--allow-root", "--ip='0.0.0.0'"]
