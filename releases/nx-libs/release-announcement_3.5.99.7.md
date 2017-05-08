# Arctica Announcement (No. 00008): Release of nx-libs (version 3.5.99.7)

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

On Friday, May 5th 2017, version 3.5.99.7 of nx-libs [has been
released](https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.7)
[1].

#### Credits

A special thanks goes to Ulrich Sibiller for tracking down a regression
bug that caused a tremendously slowed down keyboard input on high latency
connections. Thanks for that!

Another thanks goes to the Debian project for indirectly providing us
with so many build platforms. We are nearly at the point where nx-libs
builds on all architectures supported by the Debian project. (Runtime
stability is a completely different issue, we will get to this soon).

#### Changes between 3.5.99.6 and 3.5.99.7

  * Include Debian patches, re-introducing GNU/Hurd and GNU/kFreeBSD support.
    Thanks to various porters on #debian-ports and #debian-hurd for feedback
    (esp. Paul Wise, James Clark, and Samuel Thibault).
  * Revert "Switch from using libNX_X11's deprecated XKeycodeToKeysym() function
    to using XGetKeyboardMapping()."
  * Mark XKeycodeToKeysym() function as _not_ deprecated in libNX_X11 as using
    XGetKeyboardMapping() (as suggested by X.org devs) in nxagent is no option
    for us. XGetKeyboardMapping() simply creates far too many round trips for
    our taste.

### Change Log

Lists of changes (since 3.5.99.6) can be obtained from
[here](https://github.com/ArcticaProject/nx-libs/commit/5d5336541a7fb09f0164bebc63dc3113e553d720).

### Known Issues

A list of known issues can be obtained from the nx-libs issue tracker [issues].

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
server-side component). The nxagent Xserver can be used from remote
sessions (via nxcomp compression library) or as a next Xserver.

Ubuntu developers, please note: we have added nightly builds for Ubuntu
latest to our build server. At the moment, you can obtain nx-libs builds for
Ubuntu 16.10 (yakkety) and 17.04 (zenial) as nightly builds.

### References

 - [1] https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.7
 - [issues] https://github.com/ArcticaProject/nx-libs/issues
