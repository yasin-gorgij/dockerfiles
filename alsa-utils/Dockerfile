FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="alsa-utils in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t alsa-utils:1.2.7 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain alsa-utils:1.2.7"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV ALSA_UTILS=alsa-utils-1.2.7

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y automake bzip2 gettext libtool-bin make vim wget && \
    apt-get clean all && \
    wget http://www.alsa-project.org/files/pub/utils/$ALSA_UTILS.tar.bz2 && \
    tar -xf $ALSA_UTILS.tar.bz2

WORKDIR /$ALSA_UTILS
