## **Docker Commands**

---

### Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Image Management](#image-management)
4. [Container Management](#container-management)
5. [Network Management](#network-management)
6. [Volume Management](#volume-management)
7. [Docker Compose](#docker-compose)
8. [System Cleanup & Utilities](#system-cleanup--utilities)
9. [Reference & Further Reading](#reference--further-reading)

---

## Introduction

This document provides an overview of commonly used Docker commands along with examples and explanations. It covers basic to intermediate operations for managing images, containers, networks, and volumes using Docker Compose, as well as performing system cleanup.

---

## Prerequisites

- Docker installed on your machine.
- Access to Docker Hub or a private registry.
- Basic familiarity with the command line and Linux filesystem.

---

## Image Management

| Command                             | Description                          | Example                            |
| ----------------------------------- | ------------------------------------ | ---------------------------------- |
| `docker --version`                  | Display installed Docker version     | `docker --version`                 |
| `docker pull <image>`               | Download an image from a registry    | `docker pull ubuntu`               |
| `docker images`                     | List all local images                | `docker images`                    |
| `docker build -t <name> <path>`     | Build image from Dockerfile          | `docker build -t my_app .`         |
| `docker tag <id> <repo>:<tag>`      | Tag an existing image for a registry | `docker tag abc123 myrepo/app:v1`  |
| `docker push <repo>:<tag>`          | Push tagged image to registry        | `docker push myrepo/app:v1`        |
| `docker history <image>`            | Show image layer history             | `docker history ubuntu`            |
| `docker save -o <file>.tar <image>` | Save image to tar archive            | `docker save -o ubuntu.tar ubuntu` |
| `docker load -i <file>.tar`         | Load image from tar archive          | `docker load -i ubuntu.tar`        |

---

## Container Management

| Command                          | Description                                  | Example                                |
| -------------------------------- | -------------------------------------------- | -------------------------------------- |
| `docker run <image>`             | Create & start a container                   | `docker run ubuntu`                    |
| `docker run -it <image> <cmd>`   | Interactive container session                | `docker run -it ubuntu /bin/bash`      |
| `docker ps`                      | List running containers                      | `docker ps`                            |
| `docker ps -a`                   | List all containers (including stopped)      | `docker ps -a`                         |
| `docker start <id>`              | Start a stopped container                    | `docker start abc123`                  |
| `docker stop <id>`               | Stop a running container                     | `docker stop abc123`                   |
| `docker restart <id>`            | Restart container                            | `docker restart abc123`                |
| `docker rm <id>`                 | Remove a stopped container                   | `docker rm abc123`                     |
| `docker exec -it <id> <cmd>`     | Execute command in running container         | `docker exec -it abc123 /bin/bash`     |
| `docker logs <id>`               | View container logs                          | `docker logs abc123`                   |
| `docker logs -f <id>`            | Follow container logs in real-time           | `docker logs -f abc123`                |
| `docker inspect <id>`            | Detailed container info                      | `docker inspect abc123`                |
| `docker commit <id> <new_image>` | Create new image from container changes      | `docker commit abc123 my_app:v2`       |
| `docker attach <id>`             | Attach to container's std streams            | `docker attach abc123`                 |
| `docker top <id>`                | List processes inside a container            | `docker top abc123`                    |
| `docker pause <id>`              | Pause container processes                    | `docker pause abc123`                  |
| `docker unpause <id>`            | Unpause container                            | `docker unpause abc123`                |
| `docker cp <id>:<src> <dest>`    | Copy files from the container to the host    | `docker cp abc123:/var/log/app.log ./` |
| `docker diff <id>`               | Show filesystem changes in the container     | `docker diff abc123`                   |
| `docker kill <id>`               | Force-stop a running container               | `docker kill abc123`                   |
| `docker wait <id>`               | Block until container stops, print exit code | `docker wait abc123`                   |

---

## Network Management

| Command                         | Description                | Example                         |
| ------------------------------- | -------------------------- | ------------------------------- |
| `docker network ls`             | List all Docker networks   | `docker network ls`             |
| `docker network create <name>`  | Create a new network       | `docker network create my_net`  |
| `docker network inspect <name>` | Detailed network info      | `docker network inspect my_net` |
| `docker network rm <name>`      | Remove an existing network | `docker network rm my_net`      |

---

## Volume Management

| Command                        | Description         | Example                        |
| ------------------------------ | ------------------- | ------------------------------ |
| `docker volume ls`             | List all volumes    | `docker volume ls`             |
| `docker volume create <name>`  | Create a new volume | `docker volume create my_vol`  |
| `docker volume inspect <name>` | Show volume details | `docker volume inspect my_vol` |
| `docker volume rm <name>`      | Remove a volume     | `docker volume rm my_vol`      |

---

## Docker Compose

| Command                           | Description                               | Example                           |
| --------------------------------- | ----------------------------------------- | --------------------------------- |
| `docker-compose up`               | Start services from `docker-compose.yml`  | `docker-compose up`               |
| `docker-compose down`             | Stop & remove services, networks, volumes | `docker-compose down`             |
| `docker-compose build`            | Build or rebuild services                 | `docker-compose build`            |
| `docker-compose ps`               | List Compose containers                   | `docker-compose ps`               |
| `docker-compose logs`             | View logs of Compose services             | `docker-compose logs`             |
| `docker-compose exec <svc> <cmd>` | Run command in service container          | `docker-compose exec web ls /app` |
| `docker-compose pull`             | Pull service images                       | `docker-compose pull`             |
| `docker-compose stop`             | Stop services without removal             | `docker-compose stop`             |
| `docker-compose restart`          | Restart services                          | `docker-compose restart`          |
| `docker-compose rm`               | Remove stopped service containers         | `docker-compose rm`               |
| `docker-compose scale <svc>=<n>`  | Scale service instances                   | `docker-compose scale web=3`      |

---

## System Cleanup & Utilities

| Command                  | Description                                         | Example                  |
| ------------------------ | --------------------------------------------------- | ------------------------ |
| `docker system prune`    | Remove unused containers, networks, images, volumes | `docker system prune`    |
| `docker image prune`     | Remove unused/dangling images                       | `docker image prune`     |
| `docker container prune` | Remove stopped containers                           | `docker container prune` |
| `docker volume prune`    | Remove unused volumes                               | `docker volume prune`    |
| `docker network prune`   | Remove unused networks                              | `docker network prune`   |
| `docker stats`           | Live stream of container resource usage             | `docker stats`           |
| `docker events`          | Real-time event stream from Docker daemon           | `docker events`          |
| `docker info`            | System-wide Docker info                             | `docker info`            |
| `docker version`         | Detailed version information                        | `docker version`         |

---

## Reference & Further Reading

- Official Docker Documentation: [https://docs.docker.com/](https://docs.docker.com/)
- Docker CLI Reference: [https://docs.docker.com/engine/reference/commandline/cli/](https://docs.docker.com/engine/reference/commandline/cli/)
- Docker Compose Reference: [https://docs.docker.com/compose/reference/](https://docs.docker.com/compose/reference/)

---

*Prepared & compiled by Shubham Kapadnis*

https://www.linkedin.com/in/shubham-kapadnis/
