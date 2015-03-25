#bbarad/cctbx
*`bbarad/cctbx` is based on `ubuntu:14.04.2`*

**This container installs and sources cctbx for any projects that use cctbx as a backend.**

#Usage 
Building cctbx requires a large amount of ram - do not attempt to build without 5 GB of ram and/or swap available.
`docker build --rm bbarad/cctbx`
`docker run -it bbarad/cctbx /bin/bash`