# Start And Stop A Container

Docker containers can be run using compose files which can define a list of services or standalone from the command line. 

The example here will run the official Nginx image from the command line.

### Start the container

Start the container from the command line as follows:

```shell
docker run --rm -d -p 8080:80 --name web nginx
```

In the above example:

* `--rm` tells Docker to automatically remove the container when it exits
* `-d` runs the container as a daemon
* `-p` exposes the internal port 80 to external port 8080 (meaning you will access the web server on port 8080)
* `--name` specifies the name of `web` for the container
* `nginx` is the official NGINX image for the container

The container image will be downloaded from Docker Hub if it does not exist locally on first start.

### Stop the container

The same container can be stopped using:

```shell
docker stop web
```
