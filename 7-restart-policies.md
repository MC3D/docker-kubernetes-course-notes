# Docker Restart Policies

Docker restart policies define the behavior of containers when they exit or when the Docker daemon restarts. They determine whether containers are automatically restarted and under what conditions.

Here are some commonly used Docker restart policies:

- **no** (must be wrapped in quotes): This is the default restart policy. Containers will not be automatically restarted regardless of the exit status or restart conditions.
- **always**: Containers will always be automatically restarted, regardless of the exit status or restart conditions.
- **on-failure**: Containers will be automatically restarted only if they exit with a non-zero exit status, indicating a failure.
- **unless-stopped**: Containers will be automatically restarted unless they are explicitly stopped by the user. This policy ensures that containers are always running, even after system reboots or Docker daemon restarts.
- **on-failure: <max-retries>**: This policy allows you to specify the maximum number of times a container can be restarted on failure. If the container exceeds the specified number of restart attempts, it will no longer be automatically restarted.
