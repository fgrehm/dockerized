FROM ubuntu:precise
MAINTAINER Fabio Rehm "fgrehm@gmail.com"

# "Preamble" to all images on this repository
ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list && \
    apt-get update && \
    apt-get -y upgrade && \
    apt-get install -yq vim curl wget

RUN apt-get install -yq libyaml-dev

# Beets dependencies
RUN apt-get install -yq python python-pip python-dev python-setuptools

# TODO: Install pip dependencies for other beets plugins
RUN pip install flask beets

# TODO: Make this a volume
RUN mkdir -p /.config/beets
RUN echo "plugins: web\nweb:\n  host: 0.0.0.0" > /.config/beets/config.yaml

EXPOSE 8337
CMD ["/usr/local/bin/beet", "web"]
