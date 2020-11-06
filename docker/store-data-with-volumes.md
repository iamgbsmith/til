# Store Data With Volumes

Volumes are the preferred way to persist data in Docker containers and services as they allow you to back up, restore, or migrate data from one Docker host to another.

The approach outlined here creates a volume which is used in a Swarm deployment.

### Create the volume

```shell
docker volume create my-vol
```

### Inspect the volume

```shell
docker volume inspect my-vol

[
    {
        "CreatedAt": "2020-11-01T02:55:54Z",
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/my-vol/_data",
        "Name": "my-vol",
        "Options": {},
        "Scope": "local"
    }
]

```

### Reference the volume in a compose file

```yaml
version: "3.8"
services:

  data-lake:
    image: data-lake-service:latest
    ports:
      - "8080:8080"    
    volumes:
      - my-vol:/opt/app/etl

volumes:
  my-vol:
    external: true
```

### Backup data in a volume

To back up the volume’s directory (such as /var/lib/docker/volumes/my-vol), stop the container that is using the volume and copy the directory contents to another location.

### Remove a volume

```shell
docker volume rm my-vol
```

See [Using data volumes in Docker](https://docs.docker.com/storage/volumes/) for more details.

