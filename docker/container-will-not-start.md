# Container Will Not Start

If a container won't start when using a Docker compose file, check the state of containers using:

```
$ docker ps -a
```

If the container isn't listed as either running, stopped or exited, double-check the image name specified for the container in your Docker compose file matches the name of an image in the Docker image repository you are deploying from.

```
image: ${REGISTRY}/${CONTEXT}/someapp:1.0.9
```

If the name is incorrect, the container startup will fail silently.
