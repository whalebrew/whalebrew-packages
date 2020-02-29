FROM java:8-jre-alpine


RUN apk add --no-cache \
  wget \
  graphviz \
  ttf-droid \
  ttf-droid-nonlatin

ENV LANG en_US.UTF-8
ENV GRAPHVIZ_DOT /usr/bin/dot
ARG PLANTUML_VERSION=1.2020.1

RUN wget "https://downloads.sourceforge.net/project/plantuml/${PLANTUML_VERSION}/plantuml.${PLANTUML_VERSION}.jar" \
  -O /usr/share/plantuml.jar

ENTRYPOINT ["java", "-jar", "/usr/share/plantuml.jar"]
