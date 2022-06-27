FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="U-Boot in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t u-boot:v2022.04 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain u-boot:v2022.04"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV U_BOOT=u-boot-v2022.04

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y bc bison bzip2 flex gcc libncurses-dev libssl-dev make vim wget && \
    apt-get clean all && \
    wget https://source.denx.de/u-boot/u-boot/-/archive/v2022.04/$U_BOOT.tar.bz2 && \
    tar -xf $U_BOOT.tar.bz2

WORKDIR /$U_BOOT
