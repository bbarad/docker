FROM ubuntu:14.04.2
MAINTAINER benjamin barad "benjamin.barad@gmail.com"


# This minimal Dockerfile installs stable cctbx and adds it to the path. 
# Meant to be built on, but hopefully ideal for webapps with a cctbx backend.

# The release tag... this is the last published release, so I am considering it the most recent "stable" release
ENV BUILD_TAG 2013_07_05_0005

# I could probably remove this for a true minimal case... but cctbx is going to work best on a fresh python install
RUN \
  apt-get update -y && \
  apt-get install -y python2.7 python2.7-dev python-pip && \
  apt-get autoremove && \
  apt-get clean

RUN mkdir /opt/cctbx && cd /opt/cctbx
RUN curl -O http://cci.lbl.gov/cctbx_build/results/${BUILD_TAG}/cctbx_bundle.tar.gz
RUN tar -xzf cctbx_bundle.tar.gz
RUN mkdir cctbx_build && cd cctbx_build
RUN python ../cctbx_sources/libtbx/configure.py mmtbx
RUN source setpaths.sh
RUN make

RUN cd / 
