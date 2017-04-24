# Arctica Announcement (No. 00004): Release of nx-libs (version 3.5.99.3)

### Introduction

NX is a software suite which implements very efficient compression of the
X11 protocol. This increases performance when using X applications over a
network, especially a slow one.

NX (v3) has been originally developed by NoMachine and has been Free
Software ever since. Since NoMachine obsoleted NX (v3) some time back in
2013/2014, the maintenance has been continued by a versatile group of
developers. The work on NX (v3) is being continued under the project name
"nx-libs".

### Release Announcement

On Monday, Dec 19th, version 3.5.99.3 of nx-libs [has been
released](https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.3)
[1].

This release brings another major backport of libNX_X11 (to the status of
X.org's libX11 1.6.4, i.e. latest HEAD) and also a major backport of the
xtrans library (status of latest HEAD at X.org, as well). This big chunk
of work has again been performed by Ulrich Sibiller. Thanks for your work
on this.

This release is also the first version of nx-libs (v3) that has dropped
nxcompext as shared library. We discovered that shipping nxcompext as
shared library is a big design flaw as it has to be built against
header files private to the Xserver (namely, dix.h). Conclusively, code
from nxcompext was moved into the nxagent DDX [2].

Furthermore, we worked again and again on cleaning up the code base. We
dropped various files from the Xserver code shipped in nx-libs and
various compilier warnings have been amended.

In the upstream ChangeLog you will find some more items around code
clean-ups and .deb packaging, see the diff [3] on the ChangeLog file for
details. 

A very special and massive thanks to all major contributors, namely
Ulrich Sibiller, Mihai Moldovan and Vadim Troshchinskiy. Well done!!!
Also a special thanks to Vadim Troshchinskiy for fixing some regressions
in nxcomp introduced by the Unix socketeering support.

### Change Log

A list of recent changes (since 3.5.99.2) can be obtained from
[here](https://github.com/ArcticaProject/nx-libs/commit/9acd13e50c3bde9105f6143922028f0de0d4ae50).

### Known Issues from 3.5.99.2 (solved in 3.5.99.3)

This version of nx-libs now works fine again with LDFLAGS / CFLAGS having
the -pie / -fPIE hardening flags set.

### Binary Builds

You can obtain binary builds of nx-libs for Debian (jessie, stretch,
unstable) and Ubuntu (trusty, xenial) via these apt-URLs:

  * Debian: ``deb http://packages.arctica-project.org/ubuntu {jessie,stretch,sid} main``
  * Ubuntu: ``deb http://packages.arctica-project.org/ubuntu {trusty,xenial} main``

Our package server's archive key is: 0x98DE3101 (fingerprint: 7A49 CD37
EBAE 2501 B9B4  F7EA A868 0F55 98DE 3101). Use this command to make APT
trust our package server:

     wget -qO - http://packages.arctica-project.org/archive.key | sudo apt-key add -

The nx-libs software project brings to you the binary packages
``nxproxy`` (client-side component) and ``nxagent`` (nx-X11 server,
server-side component).

Ubuntu developers, please note: we have added nightly builds for Ubuntu
latest to our build server. This has been Ubuntu 16.10 so far, but we
will soon drop 16.10 support in nightly builds and add 17.04 support. 

### References

 - [1] https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.3
 - [2] https://github.com/ArcticaProject/nx-libs/pull/277
 - [3] https://github.com/ArcticaProject/nx-libs/commit/9acd13e50c3bde9105f6143922028f0de0d4ae50
