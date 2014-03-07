FROM ubuntu:precise
MAINTAINER Fabio Rehm "fgrehm@gmail.com"

ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list && \
    apt-get update && \
    apt-get -y upgrade

RUN apt-get install -yq python python-pip python-dev python-setuptools

# TODO: Move libyaml-dev above
RUN apt-get install -yq libyaml-dev

RUN pip install beets
# TODO: Move flask above
RUN pip install flask

# TODO: Make this a volume
RUN mkdir -p /.config/beets
RUN echo "plugins: web\nweb:\n  host: 0.0.0.0" > /.config/beets/config.yaml

EXPOSE 8337
CMD ["/usr/local/bin/beet", "web"]
