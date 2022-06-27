FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="Vorbis Tools in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t vorbis-tools:1.4.2 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain vorbis-tools:1.4.2"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV VORBIS_TOOLS=vorbis-tools-1.4.2

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y automake libtool-bin make pkg-config vim wget && \
    apt-get clean all && \
    wget  https://downloads.xiph.org/releases/vorbis/$VORBIS_TOOLS.tar.gz && \
    tar -xf $VORBIS_TOOLS.tar.gz

WORKDIR /$VORBIS_TOOLS
