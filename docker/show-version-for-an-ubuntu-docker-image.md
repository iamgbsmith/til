# Show Version For An Ubuntu Docker Image

__Category: Docker__

The command `uname -a` when run inside a container reports based on the running kernel, which is shared from the host OS.

You can show the version for an Ubuntu Docker image using the following command:

```shell
docker run --rm ubuntu:latest /bin/bash -c "cat /etc/lsb-release"
```

Sample output:

```shell
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=22.04
DISTRIB_CODENAME=jammy
DISTRIB_DESCRIPTION="Ubuntu 22.04.1 LTS"
```
