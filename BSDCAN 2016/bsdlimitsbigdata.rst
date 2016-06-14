.. _bsdlimitsbigdata:

____() A Big Data Perspective
=============================

The Carnegie-Melon Auton Lab used to use FreeBSD machines

Manages 40 servers, 20 desktops, countless jails

200-250 TB of data, 60 active user accounts at any time

Limitations:

Lack of hardware and software vendor support
No NVIDIA CUDO drivers - academic sites can't use their GPUs
No propietary compilers (CM needs flexibility to use a wide variety of compilers)
MATLAB is not supported and FreeMAT, GNU Octave, and SciLab don't provide a good enough alternative as MATLAB toolboxes are the primary useful feature which is not replicated in the open source alternatives
No Wolfram Mathematica, which is the de facto standard general computer algebra program.

Research Universities were generally using Solaris in the 90s. 2000s started shifting to linux and macintosh, with windows being dominant for lower levels of education.
CM generally uses Ubuntu, RedHat, and Linux distros. BSD distros are very underrepresented.

Scientific Computing

the ports collection is a volunteer project (OpenBSD and FreeBSD), the state of important ports is hit-and-miss
there is too much open source software which is required in scientific computing to make in house effort worthwhile
ATLAS, BLAS, LAPACK, Boost, GCC 5.0 and higher du to threading requirement (scientists have a hard time coding)
R is typically the first serious domain specific language that students use after hitting limits with MATLAB, Python, 
No Rocks Cluster Distribution
Hadoop and Apache Spark are finally available on FreeBSD
No Caffe
A General problem is a lot of software is developed on Ubuntu without any consideration for other Linux distros or any other OS'
Academic community doesn't need this kind of complexity/diversity in software. 

Miscallaneous issues

DoD compliance
Lack of full/paravirtualization like Xen Dom0
diversity of hardware

NetBSD

Portability appears dead, as everything except amd64, arm, and mips64 are no longer being actively developed
Devs don't use their software, no xen dom0 advertising
NetBSD dev in the room is upset, claims he uses netBSD at work (ISP) (but he uses Linux distros at home)

Dragonfly and HAMMER

There are still many issues with dragonfly
small user base, almost non-existant dev base
home use is problematic
jail infrastructure is not being updated and perhaps should be integrated with HAMMER.

pfSense

a turnkey appliance like freenas or pfsense have more features than wanted and sometimes altering the default settings or setting up custom features can break things.
