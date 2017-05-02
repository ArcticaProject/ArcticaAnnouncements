# Arctica Announcement (No. 00007): Release of remote-logon-service (version 1.0.1.1)

### Introduction

Remote Logon Service is a broker client service for tracking the
availability of remote desktop services and making that information
available via DBus.

The Remote Logon Service obtains its information from a brokerage service
like X2Go Session Broker (or Canonical's discontinued UCCS service).

Arctica's Remote Logon Service is a fork and continuation of Ubuntu's
Remote Login Service, introduced with Ubuntu 12.10 [2].

### Release Announcement

On Saturday, Apr 29th 2017, version 1.0.1.1 of remote-logon-service [has
been
released](https://github.com/ArcticaProject/remote-logon-service/releases/tag/1.0.1.1)
[1].

This is the first official release of Arctica's Remote Logon Service
after having been forked from Ubuntu's remote-login-service (shipped with
Unity Greeter's remote login feature) [3].

Recent changes:

  * completely change name space from remote-login-service to
    remote-logon-service (s/login/logon/), no overlapping path
    names anymore
  * fix some FTBFS problems during unit tests (resolved by not
    instantiating the NMClient object anymore when testing)

### Change Log

A list of changes (since 1.0.1.1) can be obtained from
[here](https://github.com/ArcticaProject/remote-logon-service/compare/debian/1.0.0-0ubuntu3...1.0.1.1).

### Known Issues

Currently none.

### Binary Builds

You can obtain binary builds of remote-logon-service for Debian (stretch,
unstable) and Ubuntu (trusty, xenial) via these apt-URLs:

  * Debian: ``deb http://packages.arctica-project.org/ubuntu {stretch,sid} main``
  * Ubuntu: ``deb http://packages.arctica-project.org/ubuntu {trusty,xenial} main``

Our package server's archive key is: 0x98DE3101 (fingerprint: 7A49 CD37
EBAE 2501 B9B4  F7EA A868 0F55 98DE 3101). Use this command to make APT
trust our package server:

     wget -qO - http://packages.arctica-project.org/archive.key | sudo apt-key add -

### References

 - [1] https://github.com/ArcticaProject/remote-logon-service/releases/tag/1.0.1.1
 - [2] http://www.omgubuntu.co.uk/2012/09/ubuntu-12-10-login-screen-adds-remote-desktop-access
 - [3] https://launchpad.net/remote-login-service
