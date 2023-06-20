# Docker Command Guide

This README file provides an overview of common Docker commands that are used to manage Docker containers, images, and resources. Each command is accompanied by a brief description of its functionality and example usage.

## Table of Contents

- [docker build](#docker-build)
- [docker create](#docker-create)
- [docker start](#docker-start)
- [docker run](#docker-run)
- [docker exec](#docker-exec)
- [docker ps](#docker-ps)
- [docker logs](#docker-logs)
- [docker stop](#docker-stop)
- [docker kill](#docker-kill)
- [docker system prune](#docker-system-prune)
- [go-to reference](#go-to-reference)

## docker build

The `docker build` command is used to build a Docker image.

```
$ docker build <build context>
```

The `<build context>` refers to the directory path that contains the files and directories needed for building the image.

When you run `docker build .`, the `.` (dot) represents the current directory as the build context. It means that all the files and directories in the current directory, including subdirectories, will be sent to the Docker daemon to be processed during the build.

## docker create

The `docker create` command is used to create a new Docker container based on a specified image without starting it.

```
$ docker create <image name>
```

This command prepares the container and returns the Container ID of the newly created container.

## docker start

The `docker start` command is used to start a stopped Docker container.

```
$ docker start <container id>
```

This command starts the specified container, identified by its Container ID or container name.

## docker run

The docker run command is used to create and start a new Docker container based on a specified image.

The basic command syntax is as follows:

```
$ docker run <image name>
```

This command checks if the specified image exists locally and creates a new container based on it. It also allocates necessary resources and starts the container.

## docker exec

The `docker exec` command is used to execute a command within a running Docker container.

```
$ docker exec <container id> <command>
```

This command allows you to interact with the container's environment and run commands as if you were inside the container itself.

## docker ps

The `docker ps` command lists the currently running Docker containers.

```
$ docker ps
```

This command displays information about the running containers, including their Container ID, Image, command being executed, creation time, status, and ports.

Note: By default, `docker ps` only shows the running containers. If you want to see all containers (including the ones that have exited), you can use the `-a` or `--all` flag:

```
$ docker ps -a
```

## docker logs

The `docker logs` command is used to fetch the logs generated by a specific Docker container.

```
$ docker logs <container id>
```

This command retrieves and displays the logs associated with the container identified by `<container id>`.

## docker stop

The `docker stop <container id>` command is used to stop a running Docker container.

```
$ docker stop <container id>
```

When you execute this command, Docker sends a SIGTERM signal to the main process running inside the container, giving it an opportunity to perform any necessary cleanup tasks before shutting down. If the process doesn't respond to the SIGTERM signal within a certain timeout period (default is 10 seconds), Docker sends a SIGKILL signal, forcefully terminating the container.

## docker kill

The `docker kill` command is used to forcefully terminate a running Docker container.

```
$ docker kill <container id>
```

This command sends a SIGKILL signal to the container's main process, immediately terminating it without any cleanup tasks.

## docker system prune

```
$ docker system prune
```

This command removes stopped containers, unused images, unused networks, and unused volumes to reclaim disk space.

Note: It's important to note that this command performs a potentially destructive operation, as it permanently deletes unused resources. Therefore, it's recommended to use it with caution and make sure you have a backup of any important data before running it.

## go-to reference

- You can use the `-p` or `--publish` flag in Docker to publish (expose) container ports and bind them to specific host ports. It enables network communication between the running container and the host or other containers.

Here's an example command using the -p flag:

```
docker run -p 8080:80 simpleweb
```

- When you include a `[command]` at the end of the `docker run <image name>` command, it overrides (replaces) the default command specified in the Docker image and executes the provided command instead.

- The `-a` or `--attach` option is used to attach the container's output to the current terminal.

```
docker start -a <container id>
```

- The `docker exec -it <container id> <command>` command is used to execute a command within a running Docker container. It allows you to interact with the container's environment and run commands as if you were inside the container itself.

- The `docker exec -it <container id> sh` command is used to start an interactive session inside a running Docker container, specifically using the `/bin/sh` shell as the command interpreter. It allows you to enter commands and interact with the container's environment as if you were inside it.