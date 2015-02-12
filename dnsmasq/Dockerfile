FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install -y dnsmasq
RUN apt-get install -y vim
#RUN apt-get -y upgrade

COPY docker-entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]