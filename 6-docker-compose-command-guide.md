# Docker Compose Command Guide

This README file provides an overview of common Docker Compose commands used for managing multi-container Docker applications. Each command is accompanied by a brief description and practical examples to help you understand its functionality.

## Table of Contents

- [docker-compose up](<#docker-compose up>)
- [docker-compose down](<docker-compose down>)
- [docker-compose ps](<docker-compose ps>)

## docker-compose up

The `docker-compose up` command is used to build, create, and start Docker containers defined in a Docker Compose file. It reads the `docker-compose.yaml` file in the current directory (or a specified file with the `-f` flag) and sets up the specified services by pulling the necessary images, creating the containers, and connecting them according to the defined configuration.

The `--build` flag is used with the `docker-compose up` command to build the Docker images before creating and starting the containers. It ensures that the latest version of the images is built, incorporating any changes made to the Dockerfiles or build contexts.

```
docker-compose up --build
```

The `--detach` or `-d` flag is used with the `docker-compose up` command to run the containers in the background and detach the terminal. It allows the containers to continue running in the background while freeing up the terminal for other commands or tasks.

```
docker-compose up -d
```

## docker-compose down

The docker-compose down command is used to stop and remove the containers, networks, and volumes created by docker-compose up. It cleans up the resources associated with the Docker Compose project, ensuring that all containers are stopped and removed from the system.

## docker-compose ps

The `docker-compose ps` command is used to display the status of containers managed by Docker Compose. It provides information about the running containers, such as their names, state, and associated services. This command is helpful for quickly checking the health and status of the containers in your Docker Compose project.
