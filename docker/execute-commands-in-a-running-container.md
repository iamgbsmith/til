# Execute Commands In A Running Container

__Category: Docker__

You can execute a command in a running Docker container by connecting to the container instance.

For example, the following will open a bash shell in interactive mode for a running container called `web-server`:

```shell
docker exec -it web-server /bin/bash
```

In the above command, the use of `-it` will keep STDIN open and allocate a psuedo-TTY so that you can type commands.

To run a background command (non-interactive) on a running container use the `-d` flag:

```shell
docker exec -d web-server touch /tmp/somefile
```
