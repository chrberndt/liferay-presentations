title: Liferay With Docker
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---

class: impact

.logo[<img src="images/liferay-waffle.svg">]

## Work in Progress

# {{title}}

christian.berndt@liferay.com

.date[
  Frankfurt am Main, 20 November 2020
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Docker Basics]
1. Using Liferay Docker Images
]

---

title: Liferay With Docker
layout: true

###.breadcrumbs[Liferay With Docker › Docker Basics]

.bottom-bar[
  {{title}}
]

---

# Docker Basics

## Overview

1. Docker Concepts & Benefits
1. Docker Images and Containers
1. The Docker Engine
1. Docker Containers and Virtual Machines
1. Essential Dockerfile Commands
1. Docker Volumes
1. Essential Docker Commands
1. docker-compose

---

# Docker Basics

## Docker Concepts & Benefits

* TODO: see https://docs.docker.com/get-started/

---

# Docker Basics

## Docker Images and Containers

* An __Image__ is an executable package that includes everything needed to run an application
* A __Container__ is a runtime instance of an image

---

# Docker Basics

## The Docker Engine

* TODO

---

# Docker Basics

## Containers and Virtual Machines

* TODO

---

# Docker Basics

## Essential Dockerfile Commands

```Dockerfile
FROM <image>[:<tag>] [AS <name>]              # Set the Base Image for subsequent instructions

RUN <command>                                 # Execute any commands in a new layer on top of the current image

CMD ["executable","param1","param2"]          # Provide defaults for an executing container

EXPOSE <port> [<port>/<protocol>...]          # Specify the network ports the container listens to at runtime

ENV <key>=<value> ...                         # Set the environment variable <key> to the value <value>

ADD [--chown=<user>:<group>] <src>... <dest>  # Copy new files, directories or remote file URLs from <src> and
                                              # add them to the filesystem of the image at the path <dest>

COPY [--chown=<user>:<group>] <src>... <dest> # Copy new files or directories from <src> and
                                              # add them to the filesystem of the container at the path <dest>

ENTRYPOINT ["executable", "param1", "param2"] # Configure a container that will run as an executable

VOLUME ["/data"]                              # Create a mount point with the specified name

USER <user>[:<group>] or <UID>[:<GID>]        # Set the user name (or UID) and optionally the user group (or GID)
                                              # to use when running the image

WORKDIR /path/to/workdir                      # Set the working directory for any RUN, CMD, ENTRYPOINT,
                                              # COPY and ADD instructions that follow
```
.footnote[
  For the complete reference see: https://docs.docker.com/engine/reference/builder/
]

---

# Docker Volumes

## Introduction

* Stored in a part of the host filesystem which is *managed by Docker* (`/var/lib/docker/volumes/` on Linux)
* Non-Docker processes should not modify this part of the filesystem
* Exist outside the lifecycle of a given container
* Only removed when you explicitly remove them
* In general the preferred way to persist data in Docker

.footnote[
  See: https://docs.docker.com/storage/
]

---

# Docker Volumes

## Create and Manage Docker Volumes

__Create a Volume__

```bash
$ docker volume create my-vol
```

__List Volumes__

```bash
$ docker volume ls
DRIVER              VOLUME NAME
local               my-vol
```

.footnote[
  See https://docs.docker.com/storage/volumes/
]

---

# Docker Basics

## Prebuilt (Official) Images

* TODO

---

# Docker Basics

## Essential Docker Commands

|                                        |                    |                                             |
| -------------------------------------- |--------------------|---------------------------------------------|
| `docker`                               |                    | List Docker CLI commands                    |
| `docker <cmd> --help`                  |                    | Explain `<cmd>`                             |
| `docker --version` or `docker version` |                    | Display Docker version info                 |              
| `docker info`                          |                    | Display system-wide information             |              
| `docker run IMAGE`                     |                    | Run a command in a new container            |              
| `docker image ls`                      |                    | List images                                 |              
| `docker container ls`                  |                    | List running containers                     |              
| `docker container ls --all`            |                    | List all containers                         |              
| `docker container ls -aq`              |                    | List all containers in quiet mode           |              
| `docker container rm <container-id>`   |                    | Remove a container with id `<container-id>` |
| `docker logs -f <container-id>`        | &nbsp;&nbsp;&nbsp; | Display (and follow) a container's log      |

---

# Docker Basics

## `docker-compose`

* Define and run multi container applications
* Define services, networks and volumes

.footnote[
  See: https://docs.docker.com/compose/
]
---

# Docker Basics

## `docker-compose.yml`

* TODO

.footnote[
  For the complete reference see: https://docs.docker.com/compose/compose-file/
]

---

# Docker Basics

## Essential docker-compose Commands

|                                        |                    |                                             |
| -------------------------------------- |--------------------|---------------------------------------------|
| `docker-compose`                       | &nbsp;&nbsp;&nbsp; | List docker-compose CLI commands            |
| `docker-compose <cmd> --help`          |                    | Explain `<cmd>`                             |
| `docker-compose build`                 |                    | Build or rebuild services                   |              
| `docker-compose up`                    |                    | Builds, (re)creates, starts, and attaches to containers for a serviceRun a command in a new container |
| `docker-compose down`                  |                    | Stops containers and removes containers, networks, volumes, and images created by `up`. |

.footnote[
  For the complete reference see: https://docs.docker.com/compose/reference/overview/
]

---

# Docker Basics

## Clean Up Commands

```bash
docker rm $(docker ps -a -q)        # Remove all stopped containers
docker image prune -a               # Remove all dangling images
docker volume prune                 # Remove all unused local volumes
```

---

class: agenda

# .inner[Liferay With Docker]

.items[
1. Docker Basics
1. .active[Using Liferay Docker Images]
]

---

title: Liferay With Docker
layout: true

###.breadcrumbs[Liferay With Docker › Using Liferay Docker Images]

.bottom-bar[
  {{title}}
]

---

# Using Liferay Docker Images

## Overview

1. Liferay Docker Container Basics
1. Liferay Container Lifecylce and API
1. Configuring Liferay Containers
1. Installing Apps and Other Artifacts to Liferay Containers
1. Patching DXP in Docker
1. Running Scripts in Liferay Containers
1. Providing Files to the Liferay Container
1. Upgrading to a New Liferay Docker Image

.footnote[
  https://learn.liferay.com/dxp/7.x/en/installation-and-upgrades/installing-liferay/using_liferay_docker_images.html
]

