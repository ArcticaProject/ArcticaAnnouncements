# Arctica Announcement (No. 00007): Release of remote-logon-config-agent (version 0.9)

### Introduction

Remote Logon Config Agent is a Python script that obtains server brokerage
information via the UCCS protocol (API/4) and makes it understandable by
the Remote Logon Service DBus Service.

Arctica's Remote Logon Config Agent is a fork and continuation of Ubuntu's
thin-client-config-agent package, introduced with Ubuntu 12.10 [2].

### Release Announcement

On Saturday, Apr 29th 2017, version 0.9 of remote-logon-config-agent [has been
released](https://github.com/ArcticaProject/remote-logon-config-agent/releases/tag/0.9)
[1].

This is the first official release of Arctica's Remote Logon Config Agent
script after having been forked from Ubuntu's thin-client-config-agent
(shipped with Unity Greeter's remote login feature) [3].

Recent changes:

  * completely change name space from thin-client-config-agent to
    remote-logon-config-agent, no overlapping path names anymore

### Change Log

A list of changes (since forking from thin-client-config-agent) can be
obtained from
[here](https://github.com/ArcticaProject/remote-logon-config-agent/commit/8952f8c85972b8246a0b69d91d7fe9b9427e1abe).

### Known Issues

Currently none.

### Binary Builds

You can obtain binary builds of remote-logon-config-agent for Debian
(stretch, unstable) and Ubuntu (trusty, xenial) via these
apt-URLs:

  * Debian: ``deb http://packages.arctica-project.org/debian {stretch,sid} main``
  * Ubuntu: ``deb http://packages.arctica-project.org/ubuntu {trusty,xenial} main``

Our package server's archive key is: 0x98DE3101 (fingerprint: 7A49 CD37
EBAE 2501 B9B4  F7EA A868 0F55 98DE 3101). Use this command to make APT
trust our package server:

     wget -qO - http://packages.arctica-project.org/archive.key | sudo apt-key add -

### References

 - [1] https://github.com/ArcticaProject/remote-logon-config-agent/releases/tag/0.9
 - [2] http://www.omgubuntu.co.uk/2012/09/ubuntu-12-10-login-screen-adds-remote-desktop-access
 - [3] https://launchpad.net/thin-client-config-agent
