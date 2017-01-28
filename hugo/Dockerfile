FROM alpine
ENV GOROOT /usr/lib/go
ENV GOPATH /gopath
ENV GOBIN /gopath/bin
ENV PATH $PATH:$GOROOT/bin:$GOPATH/bin
RUN apk update && apk --no-cache add curl git mercurial bzr go make musl-dev \
 && go get -v github.com/spf13/hugo \
 && rm -rf $GOPATH/src/* \
 && rm -rf $GOPATH/pkg/* \
 && rm -rf /usr/lib/go \
 && rm -rf /var/cache/* \
 && apk del go curl mercurial bzr git musl-dev libbz2 expat libffi gdbm ncurses-terminfo-base ncurses-terminfo ncurses-libs readline sqlite-libs python2 ca-certificates libssh2 libcurl pcre binutils-libs binutils gmp isl libgomp libatomic pkgconf libgcc mpfr3 mpc1 libstdc++ gcc libc-utils musl-utils
ENTRYPOINT ["hugo"]
