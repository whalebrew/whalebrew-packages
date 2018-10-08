# FROM mxnet/python
FROM ubuntu

LABEL io.whalebrew.name ml-notebook
LABEL io.whalebrew.config.ports '["8888:8888"]'

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -y && apt-get install -y python-pip python3-pip python-dev python3-dev python-tk wget curl unzip tree

RUN pip install --upgrade pip
RUN pip install jupyter matplotlib gluon tensorflow numpy pandas sklearn scipy keras mxnet opencv-python jsanimation torch

RUN pip3 install --upgrade pip
RUN pip3 install jupyter matplotlib gluon tensorflow numpy pandas sklearn scipy keras mxnet opencv-python torch

# Jupyter needs to create a sub directory in '.local', give the daemon permissions
RUN mkdir /.local && chmod 777 /.local
ENTRYPOINT ["jupyter", "notebook", "--allow-root", "--ip='0.0.0.0'"]
