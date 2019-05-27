FROM alpine
RUN apk add --no-cache rpm
LABEL io.whalebrew.name rpmbuild
ENTRYPOINT [ "rpmbuild" ]
CMD [ "--version" ]
