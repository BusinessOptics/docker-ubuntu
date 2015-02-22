FROM ubuntu:precise
MAINTAINER Jason Brownbridge <jason@businessoptics.biz>

# Use universe repo
# Install our custom ppa
RUN \
  RUN echo "deb http://archive.ubuntu.com/ubuntu/ $(lsb_release -sc) main universe" \
    > /etc/apt/sources.list.d/universe.list
  echo "deb http://ppa.launchpad.net/businessoptics/packages/ubuntu $(lsb_release -sc) main" \
    > /etc/apt/sources.list.d/businessoptics-packages.list \
  && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 0680B3D7 \
  && apt-get update
