# Docker Commands

## `$ docker run <image name>`

When you execute `docker run <image name>`, Docker performs the following steps:

1. Checks if the specified image exists locally. If it doesn't, Docker tries to download the image from a configured registry (such as Docker Hub) unless specified otherwise.
2. Creates a new container based on the image.
3. Allocates necessary resources (CPU, memory, network, storage, etc.) for the container.
4. Starts the container and executes the default command specified in the image's Dockerfile or any custom command provided.

`docker run` = `docker create` + `docker start`

## `$ docker run <image name> [command]`

When you include a `[command]` at the end of the `docker run <image name>` command, it overrides the default command specified in the Docker image and executes the provided command instead.

## `$ docker ps`

The `docker ps` command is used to list the currently running Docker containers on your system. It provides information about the containers such as their Container ID, Image, command being executed, creation time, status, and ports.

When you execute `docker ps`, it will display a table with the following columns:

- CONTAINER ID: A unique identifier for the container.
- IMAGE: The Docker image used to create the container.
- COMMAND: The command being executed within the container.
- CREATED: The time elapsed since the container was created.
- STATUS: The current status of the container (running, stopped, restarting, etc.).
- PORTS: The exposed ports of the container.
- NAMES: The automatically assigned (randomly generatred) or user-defined name of the container.

By default, `docker ps` only shows the running containers. If you want to see all containers (including the ones that have exited), you can use the `-a` or `--all` flag:

`$ docker ps -a`

You can use the command `docker container ls -a` as an alternative to `docker ps -a`.

## `$ docker create [options] <image name>`

The `docker create` command is used to create a new Docker container based on a specified image, but unlike `docker run`, it does not start the container immediately. Instead, it prepares the container and returns the Container ID of the newly created container.

Optional flags and parameters to customize the container's behavior, such as specifying environment variables, network settings, resource constraints, etc.

## `$ docker start <container-id>`

After using `docker create`, you can later start the container using the `docker start` command, specifying the Container ID or container name.

By separating the creation and start of the container, you have more control and flexibility over container initialization, allowing you to configure additional options before actually running the container.

Note the difference between `docker start <container-id>` and `docker start -a <container-id>` lies in how the container's output is attached to the terminal.

`docker start <container-id>`: The container's output is not attached to the terminal where the command is executed. It means that once the container starts, you won't see its output directly in your terminal. However, the container will continue running in the background.

`docker start -a <container-id>`: The `-a` or `--attach` option is used to attach the container's output to the current terminal. When you use this option, the container's output is displayed in your terminal, allowing you to see the logs, console output, and any other information produced by the container.
