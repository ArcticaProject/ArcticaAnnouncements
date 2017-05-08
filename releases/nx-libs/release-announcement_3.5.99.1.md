# Arctica Announcement (No. 00002): Release of nx-libs (version 3.5.99.1)

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

On Tuesday, Sep 13th, version 3.5.99.1 of nx-libs [has been
released](https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.1)
[1].

This release brings some code cleanups regarding displayed copyright
information and an improvement when it comes to reconnecting to already
an running session from an X11 server with a color depths setup that is
different from the X11 server setup where the NX/X11 session was
originally created on. Furthermore, an issue reported to the X2Go
developers has been fixed that caused problems on Windows clients on
copy+paste actions between the NX/X11 session and the underlying MS
Windows system. For details see [X2Go BTS, Bug
#952](http://bugs.x2go.org/952) [3].


### Change Log

A list of recent changes (since 3.5.99.0) can be obtained from
[here](https://github.com/ArcticaProject/nx-libs/commit/43f135be01f520ddcebae94723d5cbbe74259526).

### Binary Builds

You can obtain binary builds of nx-libs for Debian (jessie, stretch,
unstable) and Ubuntu (trusty, xenial) via these apt-URLs:

  * Debian: ``deb http://packages.arctica-project.org/debian {jessie,stretch,sid} main``
  * Ubuntu: ``deb http://packages.arctica-project.org/ubuntu {trusty,xenial} main``

Our package server's archive key is: 0x98DE3101 (fingerprint: 7A49 CD37
EBAE 2501 B9B4  F7EA A868 0F55 98DE 3101). Use this command to make APT
trust our package server:

     wget -qO - http://packages.arctica-project.org/archive.key | sudo apt-key add -

The nx-libs brings to you the binary packages ``nxproxy`` (client-side
component) and ``nxagent`` (nx-X11 server, server-side component).

### References

 - [1] https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.1
 - [2] https://github.com/ArcticaProject/nx-libs/commit/43f135be01f520ddcebae94723d5cbbe74259526
 - [3] http://bugs.x2go.org/952
