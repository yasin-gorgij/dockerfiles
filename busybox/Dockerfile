FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="BusyBox in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t busybox:1.34.1 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain busybox:1.34.1"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV BUSYBOX=busybox-1.34.1

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y bzip2 gcc libncurses-dev make vim wget && \
    apt-get clean all && \
    wget https://busybox.net/downloads/$BUSYBOX.tar.bz2 && \
    tar -xf $BUSYBOX.tar.bz2

WORKDIR /$BUSYBOX
