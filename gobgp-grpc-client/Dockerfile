FROM ubuntu:bionic

ENV HOME /root
WORKDIR /root
ENV GO111MODULE on
ENV PATH $PATH:/root/go/bin

RUN apt update \
 && apt install -y unzip curl wget git vim iproute2 iputils-ping net-tools

RUN curl -OL https://github.com/protocolbuffers/protobuf/releases/download/v3.7.1/protoc-3.7.1-linux-x86_64.zip \
 && unzip -o protoc-3.7.1-linux-x86_64.zip -d /usr/local bin/protoc \
 && unzip -o protoc-3.7.1-linux-x86_64.zip -d /usr/local 'include/*' \
 && rm -f protoc-3.7.1-linux-x86_64.zip


RUN apt install -y software-properties-common \
 && add-apt-repository ppa:longsleep/golang-backports \
 && apt update \
 && apt install -y golang-go

RUN git clone https://github.com/osrg/gobgp.git

RUN apt install -y python3 python3-pip \
 && python3 -m pip install grpcio \
 && python3 -m pip install grpcio-tools

WORKDIR /root/gobgp

RUN ./tools/grpc/genproto.sh

WORKDIR /root/gobgp/api

RUN python3 -m grpc_tools.protoc -I./ --python_out=. --grpc_python_out=. *.proto

WORKDIR /root
