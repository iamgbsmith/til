# Manage Sensitive Data With Secrets

__Category: Docker__

Secrets allow the management of sensisitive data in a Docker Swarm deployment. This can include a blob of data such as an SSL Certificate, SSH private key, a password or any other data that should not be stored unencrypted. Secrets can be up to 500 kb in size.

Secrets are encrypted during transit and at rest in a Docker Swarm. A secret is only accessible to those services which have been granted explicit access to it, and only while those service tasks are running.

### Create a Secret

Docker secrets can be created by reading from stdin or a file.

To create a secret from stdin:

```shell
echo ‘s1ll7p@55w0rd‘ | docker secret create some_random_secret -
```

Or, to create a secret from a file:

```shell
docker secret create some_random_secret ./pwd.txt
```
__If creating a secret from a file, delete the file once the secret has been created.__

Creating a secret from a file means that the password cannot be read from the shell history. 

### List secrets

```shell
docker secret ls
```

### Use a secret

In a Docker compose file, reference the secret as follows:

```yaml
version: "3.8"
services:

  web:
    image: nginx:latest
    ports:
      - "443:443"    
    secrets:
      - some_random_secret

networks:
  default:
    name: my-swarm-network
    external: true

secrets:
  some_random_secret:
    external: true
```

Within the Dockerfile for the image, reference the secret as an environment variable from `/run/secrets`.

```bash
env APP_PASSWORD=/run/secrets/some_random_secret
```

See [Manage sensitive data with Docker secrets](https://docs.docker.com/engine/swarm/secrets/) for more details.