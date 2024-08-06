FROM perl:5.40.0
LABEL io.whalebrew.name="graph-easy"
ENV PERL_MM_USE_DEFAULT=1
ARG VERSION=0.76
RUN cpan App::cpanminus
RUN cpanm Graph::Easy@${VERSION}
ENTRYPOINT [ "graph-easy" ]
