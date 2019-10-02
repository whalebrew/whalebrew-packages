FROM node:6

ARG VERSION
RUN npm install -g cordova ionic${VERSION+@$VERSION}
LABEL io.whalebrew.config.ports '["8100:8100","35729:35729"]'

EXPOSE 8100
ENTRYPOINT ["ionic"]
