![play][1]
# play-framework

Forked and modified from https://github.com/vojtechkraus/docker-play-framework and https://github.com/Ingensi/docker-play-framework to use most recent versions of Activator and Play framework.

Docker image which provides a typesafe activator 1.3.2, designed to launch play applications (v2.3+).
* Activator: 1.3.10
* Play version: 2.5.6 
* Java: Oracle-jdk-8u102
* OS: buildpack-deps:jessie-scm (debian jessie)

## Run your app

Your play app has to be mounted in the container in the `/app` directory. Should you want to publish your app port to the host, you must use the -p argument.

Here is an example of a docker run command:

```
docker run -d \
  -v /path/to/your/play/app:/app:rw \
  -p 80:9000 \
  geezyx/play-framework
```
In some cases, you'll need to run play with the current user:

```
docker run -d \
  -v /path/to/your/play/app:/app:rw \
  -p 80:9000 \
  -u $(id -u)
  geezyx/play-framework
```


You can also package your app, in order to do that, create a `Dockerfile` like it:

```
FROM geezyx/play-framework:latest
MAINTERNER <your@email.com>

ADD /path/to/my/play-src /app
```

## Image inheritance

This docker image inherits from the official java docker image: https://hub.docker.com/_/java/


[1]: https://www.playframework.com/assets/images/logos/play_full_color.png
