FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="libogg in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t libogg:1.3.5 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain libogg:1.3.5"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV LIB_OGG=libogg-1.3.5

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y automake libtool-bin make vim wget && \
    apt-get clean all && \
    wget https://downloads.xiph.org/releases/ogg/$LIB_OGG.tar.gz && \
    tar -xf $LIB_OGG.tar.gz

WORKDIR /$LIB_OGG
