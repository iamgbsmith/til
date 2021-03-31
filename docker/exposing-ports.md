# Exposing Ports

__Category: Docker__

Ports can be exposed from a Docker container using a short syntax or a long syntax. 

### Short Syntax

The short syntax has three options.

* Specify both ports (HOST:CONTAINER)
* Specify the container port (an ephemeral host port is chosen)
* Specify the host IP address to bind to AND both ports (the default is 0.0.0.0, meaning all interfaces)

Examples:

```yaml
ports:
  - "3000"
  - "3000-3005"
  - "8080:80"
  - "9090-9091:8080-8081"
  - "49100:22"
  - "127.0.0.1:8001:8001"
  - "127.0.0.1:5000-5010:5000-5010"
  - "127.0.0.1::5000
  - "6060:6060/udp"
  - "12400-12500:1240"
```

When specifying as `"8080:80"` it means the container is listening to tcp port 80 and the container's host is listening to port 8080. Any incoming requests to the host on port 8080 are forwarded to container on port 80.

__It is recommended to specify port numbers using strings when using a short syntax.__ 

### Long Syntax

The long syntax allows for the configuration of additional fields which can't be expressed in the short form.

* target: the port inside the container
* published: the publicly exposed port
* protocol: the port protocol (either `tcp` or `udp`)
* mode: `host` for publishing a host port on each node, or `ingress` for a swarm mode port to be load balanced

Example:

```yml
ports:
  - target: 80
    published: 8080
    protocol: tcp
    mode: ingress
```

Using this configuration, requests coming into the Docker swarm on port 8080 will be forwarded to the container on port 80.

See [Docker Compose File v3 Ports Reference](https://docs.docker.com/compose/compose-file/compose-file-v3/#ports) for more details.