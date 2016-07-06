# DRAFT::: Arctica Announcement (No. XX): Release of nx-libs (version 3.5.99.0)

## Introduction

NX is a software suite which implements very efficient compression of the
X11 protocol. This increases performance when using X applications over a
network, especially a slow one.

NX (v3) has been originally developed by NoMachine and has been Free
Software ever since. Since NoMachine obsoleted NX (v3) some time back in
2013/2014, the maintenance has been continued by a versatile group of
developers. The work on NX (v3) is being continued under the project name
"nx-libs".

## History

Until January 2015, nx-libs was more mainly a redistribution approach of
the original NX (v3) software. We (we as in mainly a group of X2Go
developers) kept changes applied to the original NoMachine sources as
minimal as possible. We also kept the original files and folders
structure. Patches had been maintained via the quilt utility on top of a
Git repository, the patches had always been kept separate. That was the
3.5.0.x series of nx-libs.

In January 2015, the characteristics of nx-libs as maintained by the X2Go
project between 2011 and 2015 changed. A decision was reached:

  - Drop quilt patching approach
  - Apply all already used patches to the code via Git
  - Clean-up the complete source code tree
  - Start backporting code from X.org
  - Add new features, upgrade API/ABI and X11 extensions

This effort is now about to be released as "nx-libs 3.6.0.0".

## Contributors

Since 2011, the nx-libs code base has to a great extent been maintained
in the context of the [X2Go Project](http://wiki.x2go.org) [1].

### Qindel Group joining in...

In 2014, developers from the [Qindel Group](http://www.qindel.com) [2]
joined the nx-libs maintenance. They found X2Go's work on nx-libs and
suggested joining forces as best as possible on hacking nx-libs.

### The Arctica Project comming up...

Starting in January 2015, the development on the 3.6.x branch of the
project was moved into a new project called the [Arctica
Project](https://arctica-project.org) [3].

### Development Funding by Qindel

In September 2015, a funding project was set up at Qindel. Since then,
the Qindel group greatly supports the development of nx-libs 3.6.x
monetarily and with provided man power. The funding project officially is
a cooperation between Qindel and DAS-NETZWERKTEAM (business run by Mike
Gabriel, long term maintainer of nx-libs). The funding is split into two
subprojects and lasts until August 2017:

  - Work on nx-libs (coordinated by DAS-NETZWERKTEAM, Mike Gabriel)
  - Work on multimedia support in remote graphical sessions (coordinated by
    Mao Chen Lee, Guangzhou Nianguan Electronics Technology Co.,Ltd)

The current nx-libs development effort is coordinated in the context of the
Arctica Project (by Mike Gabriel), with use cases in Arctica, X2Go and
TheQVD (VDI product worked on at Qindel) in mind.

### People involved

There are various people involved in nx-libs 3.6.x maintenance and
development, some of them shall be explicitly name here (in alphabetical
order of surnames):

  - Mario Becroft (long term NX contributor)
  - Nicolas Arenas Alonso (funding project coordinator at Qindel)
  - Mike DePaulo (CVE hunter)
  - Salvador Fandiño (developer, code reviewer, provided by Qindel)
  - Mike Gabriel (development coordination, developer, packager)
  - Mao Chen Lee (Arctica Project developer, advisor)
  - Jordi Marqués (Arctica Project infrastructure maintainer)
  - Mihai Moldovan (developer, code reviewer)
  - Ulrich Sibiller (developer, code reviewer)
  - Vadim Troshchinskiy (developer, code reviewer)

Some other people have contributed, but have left the project already.
Thanks for your work on nx-libs:

  - Fernando Carvajal (contributor, provided by Qindel)
  - Reinhard Tartler (contributor to X2Go)

A big thanks to everyone involved!!!

Special thanks go to Stefan Baur for employing Mihai Moldovan and handling
all the bureaucracy, so that Mihai can work on this project and get
funded for his work.

## Achievements of nx-libs 3.5.99.0

We are very close to our self-defined release goal 3.6.0. The below tasks have already been (+/-) completed for version 3.5.99.0:

  - CVE security audit (complete)
  - remove unused code (+/- complete)
  - no bundled non-X11 libraries anymore (complete)
  - complete imake cleanup (+/- complete)
  - replace as many libNX_X  - libraries by X.org's libX  - libraries
    (complete, only remaining library: libNX_X11)
  - support for iOS (nxproxy, complete)
  - Unix file socket communication for nxproxy -C <-> nxproxy -S connections
    (complete)
  - allow Unix file sockets as channel endpoints (complete)
  - new RandR based Xinerama extension (+/- complete, more QA needed)
  - nxcomp protocol clean-up (complete)
  - RandR Xserver extension upgrade to proto version 1.5 (complete, from version 1.2)
  - Composite Xserver extension upgrade to proto version 0.4 (complete, from version 0.2)
  - various ABI/API updates (with respect to X.org), so that extension backporting should
    be easy now (+/- complete)

In a [previous blog post](https://sunweavers.net/blog/node/39) [4], the
code reduction in nx-libs has already been discussed. With this
announcement, we want to give a status update about our effort of
shrinking the nx-libs code base:

```
[mike@minobo nx-libs (3.6.x)]$ cloc --match-f '.*\.(c|cpp|h)' .
    1896 text files.
    1896 unique files.                                          
    7430 files ignored.

http://cloc.sourceforge.net v 1.60  T=5.88 s (307.3 files/s, 143310.5 lines/s)
-------------------------------------------------------------------------------
Language                     files          blank        comment           code
-------------------------------------------------------------------------------
C                              958          68574          74891         419638
C/C++ Header                   730          25683          33957         130418
C++                            120          17007          11721          61292
-------------------------------------------------------------------------------
SUM:                          1808         111264         120569         611348
-------------------------------------------------------------------------------
```

The previous statistics had these sums in the last line. First the
nx-libs 3.5.0.x code tree (where we came from):

```
-------------------------------------------------------------------------------
SUM:                          5614         329279         382337        1757743
-------------------------------------------------------------------------------
```

Then the nx-libs 3.6.x status as it was on May 9th 2016:

```
-------------------------------------------------------------------------------
SUM:                          1922         118581         126783         662635
-------------------------------------------------------------------------------
```

Another 50.000 lines of code have been removed over the past two months.

## Work pending for the final 3.6.0 release goal

  - allow embedding of nxproxy into other windows (work pending)
  - Fix Xcomposite extension in Xserver (work pending)
  - nxcomp logging clean-up (work pending)
  - optimizing documentation: how to tune NX connections (work pending)
  - XServer extension upgrades:
    - XInput 1.3 -> 1.4 (work pending)
    - Xfixes 3.0 -> 5.0 (work in progress)
    - Damage 1.0 -> 1.1 (work pending)
    - Xres 1.0 -> 2.0 (work pending)
    - Sync 1.0 -> 3.0 (work pending)
    - Render 0.10 -> 0.11 (work pending)
  - Drop as many X11 related proto headers as possible

## Known Issues

There are several open issues on the nx-libs Github project space, see
https://github.com/ArcticaProject/nx-libs/issues.

## Testing the nx-libs 3.5.99.0

We are currently working on provisioning release builds and nightly
builds of nx-libs for various recent Linux distributions. Please stay
tuned and watch [Mike Gabriel's blog](https://sunweavers.net) [5]. We
already have [nightly builds of nx-libs for Debian and
Ubuntu](https://sunweavers.net/blog/node/20) [6], but there are more to
come soon.

Until now, please use the build recipes provided in the [README.md file
of the nx-libs source
tree](https://github.com/ArcticaProject/nx-libs/blob/3.6.x/README.md)
[7].

[1] http://wiki.x2go.org
[2] http://www.qindel.com
[3] https://arctica-project.org
[4] https://sunweavers.net/blog/node/39
[5] https://sunweavers.net
[6] https://sunweavers.net/blog/node/20
[7] https://github.com/ArcticaProject/nx-libs/blob/3.6.x/README.md
