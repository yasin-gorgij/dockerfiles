FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="Dropbear in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t dropbear:2022.82 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain dropbear:2022.82"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV DROPBEAR=dropbear-2022.82

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y bzip2 make vim wget && \
    apt-get clean all && \
    wget https://matt.ucc.asn.au/dropbear/$DROPBEAR.tar.bz2 && \
    tar -xf $DROPBEAR.tar.bz2

WORKDIR /$DROPBEAR
