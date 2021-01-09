# Container Will Not Start

__Category: Docker__

If a container won't start when using a Docker compose file, check the state of containers.

### Check image name

Run the following command: 

```
$ docker ps -a
```

If the container isn't listed as either running, stopped or exited, double-check the image name specified for the container in your Docker compose file matches the name of an image in the Docker image repository you are deploying from.

```
image: ${REGISTRY}/${CONTEXT}/someapp:1.0.9
```

If the name is incorrect, the container startup will fail silently.

### Check labels for container placement

If you have specified a placement label in the compose file using a format similar to `constraints: [node.labels.foo == true]` check that the label exists on a node in the cluster. If the label has not been applied, the container startup will fail silently.

Run the following command (where `node-name` is the name of the node in the cluster you are inspecting):
```
docker node inspect --format '{{ .Spec.Labels }}' node-name
```

If the label does not exist, create it:

```
docker node update --label-add foo=true node-name
```

Try restarting services after the above configuration settings have been validated.

