FROM ubuntu:precise
MAINTAINER Jason Brownbridge <jason@businessoptics.biz>

# Install our custom ppa
RUN \
  echo "deb http://ppa.launchpad.net/businessoptics/packages/ubuntu precise main" \
    > /etc/apt/sources.list.d/businessoptics-packages.list \
  && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 0680B3D7 \
  && apt-get update
