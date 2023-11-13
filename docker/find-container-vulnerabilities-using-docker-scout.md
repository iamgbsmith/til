# Find Container Vulnerabilities Using Docker Scout

__Category: Docker__

Docker Scout is a tool that can be used to find potential vulnerabilities in containers. It creates an SBOM for image layers and checks for known vulnerabilities against CVE databases.

To view a summary of vulnerabilities in a container image called `redis/redis-stack:latest` use the following command:

```shell
docker scout quickview redis/redis-stack:latest
```

To list vulnerabilities showing CVE scores, use the `cves` parameter:

```shell
docker scout cves redis/redis-stack:latest
```

To view base image update recommendations, use the `recommendations` parameter:

```shell
docker scout recommendations redis/redis-stack:latest
```

__Note:__ Docker Scout is free for up to 3 repositories. Usage beyond that requires signing up to a subscription with Docker, Inc.
