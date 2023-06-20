# Buidling Custom Images

## Simple example

1. Create project directory
2. Inside the project directory, create a `Dockerfile` with the following content:

```
# Use an existing Docker image as a base
FROM alpine

# Download and install a dependency
RUN apk add --update redis

# Tell the image what to do when it starts as a container
CMD ["redis-server"]
```

3. Open your terminal or command prompt and navigate to the project directory.
4. Build the Docker image by running the following command:

```
$ docker build .
```

Optionally, you can tag your image with a specific name and version using the `-t` option:

```
$ docker build -t <Docker username or organization name>/<name of your project or repository>:<desired version tag> .
```

For example, to tag the image as `mc3d/redis:latest`, use:

```
$ docker build -t mc3d/redis:latest .
```

Tagging the image allows for easy reference and management.

## Summary

These steps guide you through the process of creating a Docker image. The `Dockerfile` contains instructions for building the image, such as specifying the base image, installing dependencies, and defining the command to run when the container starts. By running the `docker build` command, Docker builds the image using the instructions provided in the `Dockerfile`.

User Docker ID / Project (Repo) Name / Version

## Q & A

Q: What is a base image?
A: A base image serves as the foundation or starting point for creating custom Docker images. It provides the necessary operating system and dependencies to run your application.

Q: Why did we use `apline`?
A: Why do you use Windows, MacOS, or Ubuntu? They come with a preinstalled set of programs that are useful to you! Similary, `alpine` includes a default set of programs that are useful for what we are tryin to accomplish.

Q: What is apk?
A: Alpine Package Keeper (apk) is a package manager that allows you to easily install, update, and manage software packages within the Alpine-based Docker image.
