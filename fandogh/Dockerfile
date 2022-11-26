FROM ubuntu:22.04

LABEL org.label-schema.docker-build.cmd="docker image build -t fandogh-cli:latest ." \
      org.label-schema.docker.cmd="docker container run --rm -it --name fandogh -v "$PWD":/root/services fandogh-cli:latest"
      
RUN apt-get update && apt-get upgrade -y && apt-get install -y vim python3-pip && \
    pip3 install fandogh_cli --upgrade && \
    mkdir -p /root/services

WORKDIR /root/services
