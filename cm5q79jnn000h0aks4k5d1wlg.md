---
title: "Docker Brief Board"
seoTitle: "Master Docker in Minutes: Key Concepts, Commands, and Best Practices"
seoDescription: "Quickly refresh your Docker knowledge with essential concepts, key commands, and best practices to prepare for interviews or improve container workflows."
datePublished: Fri Jan 10 2025 03:30:45 GMT+0000 (Coordinated Universal Time)
cuid: cm5q79jnn000h0aks4k5d1wlg
slug: docker
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1736368106747/ec4bb8fd-9173-4efe-bbfc-292ef682863c.png
tags: interview, docker, docker-compose, docker-images

---

## Overview
- **Docker**: Open-source platform for containerization.
- **Container**: Lightweight, portable unit for running applications with all dependencies.
- **Images**: Read-only templates used to create containers.
- **Docker Engine**: Core service running Docker.

---

## Key Concepts
### Images
- Built using **Dockerfiles**.
- Pulled from **Docker Hub** or other registries.
- Can be layered and cached.

### Containers
- Instances of Docker images.
- Created, started, stopped, and removed as needed.
- Stateless by default (use volumes for persistence).

### Dockerfile
- Script to define how an image is built.
- Key commands:
  - `FROM`: Base image.
  - `RUN`: Execute commands during image build.
  - `COPY`/`ADD`: Add files.
  - `CMD`: Default container command.
  - `EXPOSE`: Declare port.

### Volumes
- Used to persist data outside the container lifecycle.
- Types:
  - **Anonymous**: No name, tied to container lifecycle.
  - **Named**: Managed explicitly.
  - **Bind Mounts**: Link host directory to container.

---

## Docker Commands

**1. Images**

| **Command**                       | **Description**                                |
|------------------------------|-------------------------------------|
|`docker images`                      | List images.                                        |
|`docker build -t <tag> .`         | Build an image from a `Dockerfile`.  |
|`docker rmi <image>`             | Remove an image.                             |

**2. Containers**

| **Command**                           | **Description**                                     |
|---------------------------------------|-----------------------------------------------------|
|`docker ps`                            | List running containers.                            |
|`docker ps -a`                         | List all containers (including stopped).            |
|`docker run -d -p 8080:80 <image>`     | Run a container in detached mode, mapping ports.    |
|`docker exec -it <container> bash`     | Access a container's shell.                         |
|`docker stop <container>`              | Stop a running container.                           |
|`docker rm <container>`                | Remove a container.                                 |

**3. Volumes**

| **Command**                           | **Description**                                     |
|---------------------------------------|-----------------------------------------------------|
|`docker volume create <name>`          | Create a volume.                                    |
|`docker run -v <volume>:/path <image>` | Mount a volume to a container.                      |

**4. Networks**

| **Command**                           | **Description**                                     |
|---------------------------------------|-----------------------------------------------------|
|`docker network ls`                    | List networks.                                      |
|`docker network create <name>`         | Create a network.                                   |
|`docker run --network <name> <image>`  | Connect a container to a network.                   |

---

## Networking
- **Bridge**: Default, isolates containers.
- **Host**: Shares host network stack.
- **None**: Disables networking.
- Ports: Use `-p <host>:<container>` to map.

---

## Docker Compose
- Tool for defining and running multi-container applications using `docker-compose.yml`.
- Common commands:
  - `docker-compose up`: Start services.
  - `docker-compose down`: Stop services.
- Example `docker-compose.yml`:
  ```yaml
  version: '3'
  services:
    app:
      build: .
      ports:
        - "8080:80"
      volumes:
        - .:/app
      networks:
        - app-network
  networks:
    app-network:
  ```
---

## Key Features
- **Portability**: Run containers on any system with Docker installed.
- **Isolation**: Separate applications and their dependencies.
- **Efficiency**: Shares OS kernel, uses less memory compared to VMs.
- **Scalability**: Easily scale applications using orchestration tools like Kubernetes.

---

## Best Practices
- Use lightweight base images (e.g., `alpine`).
- Minimize layers in the `Dockerfile`.
- Use `.dockerignore` to exclude unnecessary files.
- Keep containers stateless; externalize state using volumes.
- Tag images properly for version control.
- Use volumes for persistent data storage.

---

## Debugging
| **Command**                 | **Description**         |
|-----------------------------|-------------------------|
|`docker inspect <container>` | Detailed info.          |
|`docker stats`               | Monitor resource usage. |
|`docker system prune`        | Clean up unused data.   |

---

## Advanced
- **Docker Swarm**: Native clustering and orchestration.
- **Kubernetes**: Advanced orchestration (Docker often used for runtime).
- **Multi-stage Builds**: Optimize images by separating build and runtime dependencies.

---

## Resources
- [Docker Documentation](https://docs.docker.com/)
- [Docker Hub](https://hub.docker.com/)

--- 