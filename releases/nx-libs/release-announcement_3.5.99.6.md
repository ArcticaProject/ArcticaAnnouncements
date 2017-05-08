# Arctica Announcement (No. 00005): Release of nx-libs (version 3.5.99.6)

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

On Friday, Apr 21st 2017, version 3.5.99.6 of nx-libs [has been
released](https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.6)
[1].

As some of you might have noticed, the release announcements for 3.5.99.4
and 3.5.99.5 have never been posted / written, so this announcement lists
changes introduced since 3.5.99.3.

#### Credits

There are alway many people to thank, so I won't mention all here. The
person I need to mention here is Mihai Moldovan, though. He virtually is
our QA manager, although not officially entitled. The feedback he gives
on code reviews is sooo awesome!!! May you be available to our project
for a long time. Thanks a lot, Mihai!!!

#### Changes between 3.5.99.4 and 3.5.99.3

  * Use RPATH in nxagent now for finding libNX_X11 (our fake libX11 with
    nxcomp support added).
  * Drop support for various archaic platforms.
  * Fix valgrind issue in new Xinerama code.
  * Regression: Fix crash due to incompletely backported code in 3.5.99.3.
  * RPM packaging review by nx-libs's official Fedora maintainer (thanks, Orion!).
  * Update roll-tarball.sh script.

#### Changes between 3.5.99.5 and 3.5.99.4

  * Support building against libXfont2 API (using Xfont2, if available in
    build environment, otherwise falling back to Xfont(1) API)
  * Support built-in fonts, no requirement anymore to have the misc fonts
    installed.
  * Various Xserver os/ and dix/ backports from X.org.
  * ABI backports: CreatePixmap allocation hints, no index in CloseScreen()
    destructors propagated anymore, SetNotifyFd ABI, GetClientCmd et al. ABI.
  * Add quilt based patch system for bundled Mesa.
  * Fix upstream ChangeLog creation in roll-tarball.sh.
  * Keystroke.c code fully revisited by Ulrich Sibiller (Thanks!!!).
  * nxcomp now builds again on Cygwin. Thanks to Mike DePaulo for providing
    the patch!
  * Bump libNX_X11 to a status that resembles latest X.org libX11 HEAD.
    (Again, thanks Ulrich!!!).
  * Various changes to make valgrind more happy (esp. uninitialized memory
    issues).
  * Hard-code RGB color values, drop previously shipped rgb.txt config file.

#### Changes between 3.5.99.6 and 3.5.99.5

  * Regression fix for 3.5.99.5: Now fonts are display correctly again after
    session resumption.
  * Prefer source tree's nxcomp to system-wide installed nxcomp headers.
  * Provide nxagent specific auto-detection code for available display
    numbers (see nxagent man page for details, under -displayfd).
  * Man page updates for nxagent (thanks, Ulrich!).
  * Make sure that xkbcomp is available to nxagent (thanks, Mihai!).
  * Switch on building nxagent with MIT-SCREEN-SAVER extension.
  * Fix FTBFS on SPARC64, arm64 and m86k Linux platforms.
  * Avoid duplicate runs of 'make build' due to flaw in main Makefile.

### Change Log

Lists of changes (since 3.5.99.3) can be obtained from
[here (3.5.99.3 -> .4)](https://github.com/ArcticaProject/nx-libs/commit/095ba65b0320be5ac864245c99da1a94f83d96eb),
[here (3.5.99.4 -> .5)](https://github.com/ArcticaProject/nx-libs/commit/3a2ecb9a5d3b54b07cb3ea54d74f80a0686821db)
and [here (3.5.99.5 -> .6)](https://github.com/ArcticaProject/nx-libs/commit/06a6a5fca31a2f104c734ce49acaaccb5ddf1718)

### Known Issues

A list of known issues can be obtained from the nx-libs issue tracker [issues].

### Binary Builds

You can obtain binary builds of nx-libs for Debian (jessie, stretch,
unstable) and Ubuntu (trusty, xenial) via these apt-URLs:

  * Debian: ``deb http://packages.arctica-project.org/debian {jessie,stretch,sid} main``
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

 - [1] https://github.com/ArcticaProject/nx-libs/releases/tag/3.5.99.6
 - [issues] https://github.com/ArcticaProject/nx-libs/issues
