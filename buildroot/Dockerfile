FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="Buildroot in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t buildroot:2022.02.5 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain buildroot:2022.02.5"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV BUILDROOT=buildroot-2022.02.5

RUN apt-get update && \
    #apt-get upgrade -y && \
    apt-get install -y bc binutils build-essential bzip2 cpio file gcc g++ gzip libncurses-dev libssl-dev make patch perl python3 rsync sed tar unzip vim wget && \
    apt-get clean all && \
    wget https://buildroot.org/downloads/$BUILDROOT.tar.gz && \
    tar -xf $BUILDROOT.tar.gz

WORKDIR /$BUILDROOT

