FROM haskell:8

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    graphviz \
  && rm -rf /var/lib/apt/lists/*

RUN cabal update \
  && cabal install erd --allow-newer

ENTRYPOINT ["erd"]
