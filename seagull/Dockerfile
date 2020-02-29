FROM ubuntu:18.04

RUN apt-get update
RUN apt-get -y install build-essential curl git libglib2.0-dev ksh bison flex vim tmux
RUN mkdir -p ~/opt/src
RUN git clone https://github.com/codeghar/Seagull.git ~/opt/src/seagull &&\
  cd ~/opt/src/seagull &&\
  git branch build master &&\
  git checkout build
RUN cd ~/opt/src/seagull/seagull/trunk/src &&\
  curl --create-dirs -o ~/opt/src/seagull/seagull/trunk/src/external-lib-src/sctplib-1.0.15.tar.gz http://www.sctp.de/download/sctplib-1.0.15.tar.gz &&\
  curl --create-dirs -o ~/opt/src/seagull/seagull/trunk/src/external-lib-src/socketapi-2.2.8.tar.gz http://www.sctp.de/download/socketapi-2.2.8.tar.gz
RUN cd ~/opt/src/seagull/seagull/trunk/src &&\
  curl --create-dirs -o ~/opt/src/seagull/seagull/trunk/src/external-lib-src/openssl-1.0.2e.tar.gz https://www.openssl.org/source/openssl-1.0.2e.tar.gz &&\
  ksh build-ext-lib.ksh
RUN cd ~/opt/src/seagull/seagull/trunk/src &&\
  ksh build.ksh -target clean &&\
  ksh build.ksh -target all
RUN cp ~/opt/src/seagull/seagull/trunk/src/bin/* /usr/local/bin
ENV LD_LIBRARY_PATH /usr/local/bin
RUN mkdir -p /opt/seagull &&\
  cp -r ~/opt/src/seagull/seagull/trunk/src/exe-env/* /opt/seagull
RUN [ "/bin/bash", "-c", "mkdir -p /opt/seagull/{diameter-env,h248-env,http-env,msrp-env,octcap-env,radius-env,sip-env,synchro-env,xcap-env}/logs" ]

ENV PATH $PATH:/opt/seagull

ENTRYPOINT [ "seagull" ]
