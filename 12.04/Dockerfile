FROM ubuntu:precise
MAINTAINER Jason Brownbridge <jason@businessoptics.biz>
# Set environment variables for apt
ENV LC_ALL=C
ENV DEBIAN_FRONTEND=noninteractive 
# Refresh apt and enable Ubuntu Universe and Multiverse.
RUN \
  rm -Rf /var/lib/apt/lists/* /etc/apt/sources.list.d/* && \
  sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list && \
  sed -i 's/^#\s*\(deb.*multiverse\)$/\1/g' /etc/apt/sources.list && \
  apt-get update
# Installed required tools for apt
RUN apt-get -y install --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  python-software-properties \
  software-properties-common
# Install custom ppas
RUN \
  apt-add-repository ppa:businessoptics/packages && \
  apt-add-repository ppa:chris-lea/node.js
# Update again to bring in new packages
RUN apt-get update
# Install some packages needed for python building
RUN apt-get -y install --no-install-recommends \
    apt-transport-s3 \
    build-essential \
    curl \
    git \
    nodejs \
    pkg-config \
    python2.7 \
    python2.7-dev \
    python-distribute \
    python-pip \
    wget
# Remove buggy setuptools
RUN rm -f /usr/lib/python2.7/dist-packages/setuptools.egg-info
# Use latest packages from pip rather than ubuntu
RUN pip install -U pip
RUN pip install -U distribute
RUN pip install -U setuptools
# Remove apt lists
RUN rm -Rf rm -rf /var/lib/apt/lists/*
