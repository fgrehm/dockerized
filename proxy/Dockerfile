FROM ubuntu:precise
MAINTAINER Fabio Rehm "fgrehm@gmail.com"

# "Preamble" to all images on this repository
ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list && \
    apt-get update && \
    apt-get -y upgrade && \
    apt-get install -yq vim curl wget

# Install polipo
RUN apt-get install -y polipo

# Configure polipo
RUN echo "proxyAddress = \"0.0.0.0\"" > /etc/polipo/config
RUN echo "proxyPort = 3128" >> /etc/polipo/config

VOLUME ["/var/cache/polipo"]
EXPOSE 3128
CMD ["/usr/bin/polipo","-c","/etc/polipo/config","daemonise=false"]
