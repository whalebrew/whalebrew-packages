# FROM mxnet/python
FROM jupyter/pyspark-notebook

LABEL io.whalebrew.name ml-notebook
LABEL io.whalebrew.config.ports '["8888:8888"]'
LABEL io.whalebrew.config.volumes '["${PWD}:~/work"]'

ENV DEBIAN_FRONTEND noninteractive
ENV GRANT_SUDO yes

USER root

RUN apt-get update -y && apt-get install -y python3-pip python3-dev python-tk wget curl unzip tree

# RUN pip3 install --upgrade pip
RUN pip install opencv-python gym awscli seaborn onnx featuretools

# Jupyter needs to create a sub directory in '.local', give the daemon permissions
# RUN mkdir /.local && chmod 777 /.local

USER jovyan

RUN conda update -n base conda
RUN conda install -y -c conda-forge tensorflow mxnet keras xgboost rise
RUN conda install -y -c pytorch pytorch torchvision
RUN mkdir ~/.local && chmod 777 ~/.local

ENTRYPOINT ["/usr/local/bin/start-notebook.sh"]
