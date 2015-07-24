# Repose Docker

[![dockeri.co](http://dockeri.co/image/dimtruck/repose-docker)](https://registry.hub.docker.com/u/dimtruck/repose-docker/)

[![issues](https://img.shields.io/github/issues/dimtruck/repose_docker.svg) ![stars](https://img.shields.io/github/stars/dimtruck/repose_docker.svg)](https://github.com/dimtruck/repose_docker)

## What is Repose?

Repose provides solutions to API processing tasks such as authentication, rate limiting, API validation, HTTP Request logging, and much more. It is an open-source RESTful middleware platform that is highly scalable and extensible.

See: [http://www.openrepose.org/](http://www.openrepose.org/)

## How to run?

### If you want an out of the box Repose solution: 

```
docker run -d -p 8080:8080 -p 9777:9777 --name myrepose dimtruck/repose
```

### If you want to attach your local repose configurations:

```
docker run -d -v my_config_directory:/etc/repose -p 8080:8080 -p 9777:9777 --name myrepose dimtruck/repose
```

### If you want to run with a volume container (preferred):

```
docker create -v my_config_directory:/etc/repose:Z --name reposeconfigs dimtruck/repose /bin/bash
docker run -d --volumes-from reposeconfigs --name myrepose dimtruck/repose
```

The second docker command can now be used in all of your ci pipelines (especially if you push it to your private hub).
