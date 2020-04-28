FROM node:6
LABEL io.whalebrew.name cfn-create-or-update

ARG VERSION
RUN npm install -g cfn-create-or-update${VERSION+@$VERSION}
ENTRYPOINT ["cfn-create-or-update"]
