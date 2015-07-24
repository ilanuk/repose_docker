FROM ubuntu:14.04

MAINTAINER Dimitry Ushakov <dimitry.ushakov@rackspace.com>

RUN apt-get install -y wget
RUN wget -O - http://repo.openrepose.org/debian/pubkey.gpg | apt-key add - && echo "deb http://repo.openrepose.org/debian stable main" > /etc/apt/sources.list.d/openrepose.list
RUN apt-get update && apt-get install -y repose-valve repose-filter-bundle repose-extensions-filter-bundle

EXPOSE 8080 9777

CMD java  -Xmx512M -Xms512M -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/tmp/dump-repose.hprof -XX:MaxPermSize=128M -jar /usr/share/repose/repose-valve.jar -c /etc/repose

