[![Docker Pulls](https://img.shields.io/docker/pulls/weldpua2008/net-snmp.svg)](https://hub.docker.com/r/weldpua2008/net-snmp/)
[![Docker Stars](https://img.shields.io/docker/stars/weldpua2008/net-snmp.svg)](https://hub.docker.com/r/weldpua2008/net-snmp/)
[![dockeri.co](http://dockeri.co/image/weldpua2008/net-snmp)](https://hub.docker.com/r/weldpua2008/net-snmp/)


docker-net-snmp
===================
These are base docker images that include net-snmp.  

## Description
base image with Net-SNMP binaries installed. By default the image starts a generic trap receiver (which dumps what it receives into /trap.log) for testing, but it willl accept any SNMP command.

## Examples
Standard generic receiver:

    docker run -d --name trap_sink weldpua2008/net-snmp
    docker-enter trap_sink cat trap.log

Sending a test trap

    docker run --rm=true elcolio/net-snmp snmptrap -v 1 -c public $DESTINATION_IP .1.3.6.1.6.3 "" 0 0 coldStart.0

Can be combined with [Samplicator][1] for a local-logging trap proxy.


  

Requirements
=====================================

* docker

Obtaining these Images from DockerHub
=====================================

This content on DockerHub lives at https://hub.docker.com/r/weldpua2008/net-snmp/

* This images on DockerHub will be updated periodically.

Disclaimer
=============================

This is currently a work in progress, I am not responsible and shall not
be held responsible in any manner if this tool causes loss of data, hardware
faults, act of gods, invocation of old or ancient ones, elder gods and other
horrors from the depths.

Questions?
==========

If you'd like to talk about Ansible+Docker, stop by the .


  [1]: https://registry.hub.docker.com/u/weldpua2008/samplicator/