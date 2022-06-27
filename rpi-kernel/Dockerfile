FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="Raspberry Pi kernel in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t rpi-kernel:all-versions ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain rpi-kernel:all-versions"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y bc bison flex gcc git libncurses-dev libssl-dev make vim xz-utils && \
    apt-get clean all && \
    git clone https://github.com/raspberrypi/linux.git

WORKDIR /linux
