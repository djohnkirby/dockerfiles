# Shinken Docker installation
# usage
# run -it -p 7767:7767 -p 80:80 shinken

FROM ubuntu:trusty
MAINTAINER Daniel Kirby dk@adcade.com

RUN apt-get update

#Install Shinken, Nagios plugins, nginx, and supervisord
RUN         apt-get update && apt-get install -y python-pip \
                python-pycurl \
                python-cherrypy3 \
                nagios-plugins \
                libsys-statistics-linux-perl \
                nginx \
                supervisor \
		&& \
                apt-get -y autoremove && \
                apt-get clean

#Add the shinken user AND make it a sudoer.
RUN         useradd --create-home shinken && \
	    usermod -G sudo shinken && \
                pip install shinken

# Install mongodb
RUN apt-get install -y mongodb python-pymongo
RUN shinken --init
RUN shinken install mod-mongodb
#RUN service shinken stop

RUN service shinken start