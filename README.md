# Repose Docker

[![dockeri.co](http://dockeri.co/image/dimtruck/repose-docker)](https://registry.hub.docker.com/u/dimtruck/repose-docker/)

[![issues](https://img.shields.io/github/issues/dimtruck/repose_docker.svg) ![stars](https://img.shields.io/github/stars/dimtruck/repose_docker.svg)](https://github.com/dimtruck/repose_docker)

## What is Repose?

Repose provides solutions to API processing tasks such as authentication, rate limiting, API validation, HTTP Request logging, and much more. It is an open-source RESTful middleware platform that is highly scalable and extensible.

See: [http://www.openrepose.org/](http://www.openrepose.org/)

## How to run?

### If you want an out of the box Repose solution: 

```
docker run -d -p 8080:8080 -p 9777:9777 --name myrepose dimtruck/repose-docker:ubuntu-14.04-latest
```

### If you want to attach your local repose configurations:

```
docker run -d -v my_config_directory:/etc/repose -p 8080:8080 -p 9777:9777 --name myrepose dimtruck/repose-docker:ubuntu-14.04-latest
```

### If you want to run with a volume container (preferred):

```
tar -cv test_repose_configs/* | docker run -i --name repose-conf dimtruck/repose-docker:ubuntu-14.04-latest /bin/bash -c 'tar -xv'
docker run -d --volumes-from repose-conf -p 8080:8080 -p 9777:9777 --name myrepose dimtruck/repose-docker:ubuntu-14.04-latest
```

The second docker command can now be used in all of your ci pipelines (especially if you push it to your private hub).
