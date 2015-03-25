FROM python:2.7
MAINTAINER Benjamin Barad "benjamin.barad@gmail.com"
 
# This minimal Dockerfile installs stable cctbx and adds it to the path.
# Meant to be built on, but hopefully ideal for webapps with a cctbx backend.
 
# The release tag... this is the last published release, so I am considering it the most recent "stable" release
ENV BUILD_TAG 2013_07_05_0005
 
RUN       mkdir -p /opt/cctbx
WORKDIR   /opt/cctbx
ADD       http://cci.lbl.gov/cctbx_build/results/${BUILD_TAG}/cctbx_bundle.tar.gz /opt/cctbx/
RUN       tar -xzf cctbx_bundle.tar.gz
RUN       mkdir -p cctbx_build
WORKDIR   cctbx_build
RUN       python ../cctbx_sources/libtbx/configure.py mmtbx
RUN       make

ENV PATH /opt/cctbx/cctbx_build/bin:$PATH
 
WORKDIR   /
CMD       ["bash"]
