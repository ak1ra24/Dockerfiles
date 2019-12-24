FROM ubuntu:18.04

MAINTAINER Shogo Maeda

RUN apt update && apt install -y wget curl gnupg git software-properties-common iproute2 iputils-ping kmod vim traceroute tcpdump build-essential telnet

RUN curl -s https://packagecloud.io/install/repositories/fdio/1904/script.deb.sh | bash

RUN apt install -y vpp vpp-plugin-core

ADD ./startup.conf /etc/vpp/startup.conf

ADD ./vpp.conf /etc/vpp/vpp.conf
