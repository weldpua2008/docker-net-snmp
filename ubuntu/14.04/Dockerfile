FROM ubuntu:14.04

MAINTAINER Valeriy Solovyov <weldpua2008@gmail.com>

RUN export  DEBIAN_FRONTEND=noninteractive && \
    apt-get update && \
    apt-get -y install snmp snmpd snmp-mibs-downloader && \
    rm -r /var/lib/apt/lists/*

EXPOSE 161:161/udp

CMD ["snmptrapd", "-CdfLf", "/trap.log","--disableAuthorization=yes"]

