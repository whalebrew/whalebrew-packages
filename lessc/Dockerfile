FROM node:14-alpine

ARG VERSION
RUN npm install -g less${VERSION+@$VERSION}

ENTRYPOINT ["lessc"]
