FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="zlib in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t zlib:1.2.12 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain zlib:1.2.12"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV ZLIB=zlib-1.2.12

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y make vim wget && \
    apt-get clean all && \
    wget https://zlib.net/$ZLIB.tar.gz && \
    tar -xf $ZLIB.tar.gz

WORKDIR /$ZLIB
