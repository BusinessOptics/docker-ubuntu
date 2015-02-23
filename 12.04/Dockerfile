FROM ubuntu:precise
MAINTAINER Jason Brownbridge <jason@businessoptics.biz>

# Use universe repo
# Install our custom ppa
RUN \
  echo "deb http://archive.ubuntu.com/ubuntu/ $(lsb_release -sc) main universe" \
    > /etc/apt/sources.list.d/universe.list
  echo "deb http://ppa.launchpad.net/businessoptics/packages/ubuntu $(lsb_release -sc) main" \
    > /etc/apt/sources.list.d/businessoptics-packages.list \
  && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 0680B3D7
# Update package lists
RUN apt-get update
# Install some packages needed for python building
RUN apt-get -y install --no-install-recommends \
    build-essential \
    git \
    pkg_config \
    python2.7 \
    python2.7-dev \
    python-distribute \
    python-pip
# Use latest packages from pip rather than ubuntu
RUN pip install -U pip
RUN pip install -U distribute
