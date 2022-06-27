FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="libvorbis in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t libvorbis:1.3.7 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain libvorbis:1.3.7"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV LIB_VORBIS=libvorbis-1.3.7

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y automake libtool-bin make vim wget && \
    apt-get clean all && \
    wget  https://downloads.xiph.org/releases/vorbis/$LIB_VORBIS.tar.gz && \
    tar -xf $LIB_VORBIS.tar.gz

WORKDIR /$LIB_VORBIS
