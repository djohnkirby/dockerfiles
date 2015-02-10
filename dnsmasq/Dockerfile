FROM ubuntu:14.04

RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y dnsmasq
RUN apt-get install -y emacs

RUN echo 'listen-address=127.0.0.1' >> /etc/dnsmasq.conf
