# What Is A Docker Digest

__Category: Docker__

Docker images that use the v2 or later format are named using the format `name:[tag][@digest]` where the digest is a SHA256 hash of a specific manifest, regardless of any tags. As long as the input used to generate the image is unchanged, the digest value is predictable.

* Docker image tags are mutable, meaning they can be changed over time. 
* Docker prioritizes the digest specified and runs that regardless of whether the tag is, or ever was existent, or pointing to the referenced digest.
* For security reasons, you should reference docker images using the SHA256 digest. An attack that overwrites a mutable tag, has no effect on what is running.

Digests for pulled images can be listed by running `docker images --digests` from the command line.

Output:

```shell
REPOSITORY                           TAG       DIGEST                                                                    IMAGE ID       CREATED         SIZE
nginx                                latest    sha256:ecc068890de55a75f1a32cc8063e79f90f0b043d70c5fcf28f1713395a4b3d49   b692a91e4e15   5 days ago      142MB
```

Run the container using the image digest, omitting the use of the tag:

```shell
docker run --rm -d -p 8080:80 --name web nginx@sha256:ecc068890de55a75f1a32cc8063e79f90f0b043d70c5fcf28f1713395a4b3d49
c7785c6414eaea9225e24cc908c16f548ed05b48b2b069edd367038305c2740f
```
