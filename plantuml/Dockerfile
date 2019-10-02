FROM java:8-jre-alpine

ENV LANG en_US.UTF-8
ARG VERSION=8056
ENV GRAPHVIZ_DOT /usr/bin/dot

RUN apk add --no-cache \
  wget \
  graphviz \
  ttf-droid \
  ttf-droid-nonlatin

RUN wget "https://downloads.sourceforge.net/project/plantuml/plantuml.${VERSION}.jar" \
  -O /usr/share/plantuml.jar

ENTRYPOINT ["java", "-jar", "/usr/share/plantuml.jar"]
