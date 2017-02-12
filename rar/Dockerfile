FROM alpine
RUN apk add --no-cache make
RUN wget http://www.rarlab.com/rar/rarlinux-5.4.0.tar.gz && \
	tar -xzvf rarlinux-5.4.0.tar.gz && \
	cd rar && \
	make && \
	mv rar_static /usr/local/bin/rar
ENTRYPOINT ["rar"]
