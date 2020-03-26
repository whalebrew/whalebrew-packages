FROM alpine as build
RUN apk add --no-cache make

RUN mkdir /dl
RUN wget -O - https://www.rarlab.com/rar/rarlinux-x64-5.8.0.tar.gz | tar -xzf - -C dl

FROM debian:stable-slim
RUN apt-get update && apt-get install libstdc++6 libc6 libgcc1
COPY --from=build /dl/rar/rar /usr/local/bin/rar
COPY --from=build /dl/rar/rarfiles.lst /etc/
COPY --from=build /dl/rar/default.sfx /usr/local/lib/
ENTRYPOINT ["/usr/local/bin/rar"]
