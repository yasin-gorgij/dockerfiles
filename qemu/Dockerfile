FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="QEMU in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t qemu:7.0.0 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain qemu:7.0.0"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV QEMU=qemu-7.0.0

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y gcc libglib2.0-dev libpixman-1-dev make \
    mtd-utils ninja-build pkg-config python3 vim wget xz-utils && \
    apt-get clean all && \
    wget https://download.qemu.org/$QEMU.tar.xz && \
    tar xvJf $QEMU.tar.xz && \
    cd $QEMU && \
    ./configure && \
    make -j$(nproc) && \
    make install

