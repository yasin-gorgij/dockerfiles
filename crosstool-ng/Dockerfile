FROM ubuntu:22.04

ARG BUILD_DATE

LABEL maintainer="Yasin Gorgij"
LABEL description="Crosstool-NG in Ubuntu"
LABEL docker.build="docker image build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t crosstool-ng:1.25.0 ."
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.docker.cmd="docker container run --rm -it -v $HOME/dev/artifacts/toolchain:/toolchain crosstool-ng:1.25.0"
LABEL org.label-schema.vcs-url="https://github.com/yasin-gorgij/dockerfiles"

ENV CT_EXPERIMENTAL=y \
    CT_ALLOW_BUILD_AS_ROOT=y \
    CT_ALLOW_BUILD_AS_ROOT_SURE=y \
    CROSSTOOL_NG=crosstool-ng-1.25.0

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y autoconf automake bison bzip2 \
    flex g++ gawk gcc git gperf help2man libncurses5-dev \
    libstdc++6 libtool libtool-bin make meson ninja-build \
    patch python3-dev rsync texinfo unzip vim wget xz-utils && \
    apt-get clean all && \
    wget http://crosstool-ng.org/download/crosstool-ng/$CROSSTOOL_NG.tar.bz2 && \
    tar -xf $CROSSTOOL_NG.tar.bz2 && \
    cd $CROSSTOOL_NG && \
    ./bootstrap && \
    ./configure --prefix=/usr/local/crosstool-ng && \
    make -j$(nproc) && \
    make install && \
    ln -s /usr/local/crosstool-ng/bin/ct-ng /usr/local/bin/ct-ng

WORKDIR /toolchain
