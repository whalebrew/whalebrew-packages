FROM alpine

RUN apk add --no-cache graphviz

LABEL io.whalebrew.name dot 
ENTRYPOINT [ "dot" ]
CMD [ "--version" ]
