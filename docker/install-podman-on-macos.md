# Install Podman On MacOS

__Category: Docker__

Podman is alternative to the Docker container runtime and is supported on Linux, macOS and Windows. 

To install on macOS:

```shell
brew install podman
```

To show the installed version:

```shell
podman --version
```

Initialise podman using the following command:

```shell
podman machine init
```

Start podman:

```shell
podman machine start
```

Podman will be operational when you see `Machine "podman-machine-default" started successfully` at the console.

Stop podman:

```shell
podman machine stop
```
