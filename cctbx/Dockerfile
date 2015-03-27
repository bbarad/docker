FROM python:2.7
MAINTAINER Benjamin Barad "benjamin.barad@gmail.com"
 
# This minimal Dockerfile installs the latest cctbx from svn and adds it to the path.
# Meant to be built on, but hopefully ideal for webapps with a cctbx backend.
 
RUN       mkdir -p /opt/cctbx
WORKDIR   /opt/cctbx
RUN       svn export svn://svn.code.sf.net/p/cctbx/code/trunk/libtbx/auto_build/bootstrap.py
RUN       python bootstrap.py --builder=cctbx --with-python=python

ENV PATH /opt/cctbx/build/bin:$PATH
 
WORKDIR   /
CMD       ["bash"]
