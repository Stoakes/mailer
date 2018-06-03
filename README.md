# Stoakes mailer

> Containerized smtp server (Debian + postfix) that works out of the box.

![](https://img.shields.io/docker/stars/stoakes/mailer.svg)![](https://img.shields.io/docker/pulls/stoakes/mailer.svg)
![](https://img.shields.io/docker/automated/stoakes/mailer.svg)
![](https://images.microbadger.com/badges/image/stoakes/mailer.svg)

This image is a configuration free Debian stretch running postfix image. It provides a SMTP configured for websites to send emails from any container connected to the docker network.

Contrary to other available images, it has a low number of layer and is designed to be as small as possible. (Even though we are using Debian)

## Available Versions

You can see all images available to pull from Docker Hub via the [Tags page](https://hub.docker.com/r/stoakes/mailer/tags/).

## Usage Example

**Standalone**

```
docker run stoakes/mailer
```

**Docker-compose**

```
version: "2"

services:

    web:
        image: whatever
        depends_on:
           - mailer

    mailer:
        image: stoakes/mailer
    
```

Then use the mailer in your web container (pseudo code)

```
    mailer_transport:  smtp
    mailer_host:       mailer
    mailer_user:       ~ # That means none
    mailer_password:   ~
```

## Features

Running on Debian Stretch

 * Postfix
 * Syslog-ng to retrieve postfix logs

## Environment Variables

None

## Maintainers

[Stoakes](https://github.com/stoakes)
