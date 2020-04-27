FROM node:6

ARG VERSION
RUN npm install -g less${VERSION+@$VERSION}

ENTRYPOINT ["lessc"]
