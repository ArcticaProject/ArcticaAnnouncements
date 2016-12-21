# Arctica Announcement (No. 00003): Release of nx-libs (version 3.5.99.2)

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

On Thursday, Oct 13th, version 3.5.99.2 of nx-libs [has been
released](https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.2)
[1].

This release brings a major backport of libNX_X11 to the status of libX11
1.3.4 (as provided by X.org). On top of that, all CVE fixes provided for
libX11 by the Debian X11 Strike Force and the Debian LTS team got
cherry-picked to libNX_X11, too. This big chunk of work has been
performed by Ulrich Sibiller and there is more to come. We currently have
a pull request pending review that backports more commits from libX11
(bumping the status of libNX_X11 to the state of libX11 1.6.4, which is
the current HEAD on the X.org Git site).

Another big clean-up performed by Ulrich is the split-up of XKB code
which got symlinked between libNX_X11 and nx-X11/programs/Xserver. This
brings in some code duplications but allows maintaing the nxagent Xserver
code and the libNX_X11 code separately.

In the upstream ChangeLog you will find some more items around code
clean-ups and .deb packaging, see the diff [2] on the ChangeLog file for
details. 

So for this releas, a very special and massive thanks goes to Ulrich
Sibiller!!! Well done!!!

### Change Log

A list of recent changes (since 3.5.99.1) can be obtained from
[here](https://github.com/ArcticaProject/nx-libs/commit/29e29342ee73fcd52d3b67bebb4fc7e84df898fd).

### Known Issues

This version of nx-libs is known to segfault when LDFLAGS / CFLAGS have
the -pie / -fPIE hardening flags set. This issue is currently under
investigation.

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

 - [1] https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.2
 - [2] https://github.com/ArcticaProject/nx-libs/commit/29e29342ee73fcd52d3b67bebb4fc7e84df898fd
