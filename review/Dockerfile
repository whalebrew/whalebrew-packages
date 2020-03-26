# This file is based on https://github.com/kmuto/review/blob/master/Dockerfile.
# See https://github.com/kmuto/review/blob/master/COPYING for License.

FROM debian:sid

LABEL io.whalebrew.name review

ENV REVIEW_VERSION 3.2.0

RUN set -x && \
    apt-get update && \
    apt-get install -y --no-install-recommends git-core ruby locales zip && \
    apt-get install -y --no-install-recommends texlive-lang-cjk texlive-lang-japanese texlive-fonts-recommended texlive-latex-extra ghostscript && \
    rm -rf /var/lib/apt/lists/*

RUN set -x && \
    gem install review:$REVIEW_VERSION rake bundler --no-rdoc --no-ri

ENTRYPOINT ["review"]
