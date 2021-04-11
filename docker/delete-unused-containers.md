# Delete Unused Containers

__Category: Docker__

Running the `docker ps -a` might show stopped containers or dangling images which are using disk space.

These can be safely deleted by running the following command:

```shell
docker system prune
```

The output from this command will be a list of deleted containers and the total amount of reclaimed disk space.
