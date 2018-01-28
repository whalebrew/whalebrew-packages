# FROM mxnet/python
FROM ubuntu

LABEL io.whalebrew.name ml-notebook
LABEL io.whalebrew.config.ports '["8888:8888"]'

RUN apt-get update -y
RUN apt-get install -y python-pip python3-pip python-dev python3-dev

RUN pip install --upgrade pip
RUN pip install jupyter matplotlib gluon tensorflow numpy pandas sklearn scipy keras

RUN pip3 install --upgrade pip
RUN pip3 install jupyter matplotlib gluon tensorflow numpy pandas sklearn scipy keras

# Jupyter needs to create a sub directory in '.local', give the daemon permissions
RUN mkdir /.local && chmod 777 /.local
ENTRYPOINT ["jupyter", "notebook", "--allow-root", "--ip='0.0.0.0'"]
