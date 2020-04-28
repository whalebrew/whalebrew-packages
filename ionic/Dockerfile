FROM node:14-alpine

ARG VERSION
RUN npm install -g cordova @ionic/cli${VERSION+@$VERSION}
LABEL io.whalebrew.config.ports '["8100:8100","35729:35729"]'

EXPOSE 8100
ENTRYPOINT ["ionic"]
