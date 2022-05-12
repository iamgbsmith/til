# Generate A Software Bill of Materials

__Category: Docker__

Docker Desktop 4.7.0 and above provides an experimental feature to generate a Software Bill of Materials (SBOM) for a Docker container using `docker sbom`. Default ouptut is to the console in tabular format showing the name, version, and type of dependency (for example, Java archive, Debian package).

The `docker sbom` command has options for outputting SBOM in the standard SPDX and CycloneDX formats in addition to GitHub and native Syft formats. 

For example, to generate an SBOM in table format at the console for the nginx container image:

```shell
docker sbom nginx
```

Output:

```shell
NAME                       VERSION                         TYPE
adduser                    3.118                           deb
apt                        2.2.4                           deb
base-files                 11.1+deb11u2                    deb
base-passwd                3.5.51                          deb
bash                       5.1-2+b3                        deb
bsdutils                   1:2.36.1-8                      deb
ca-certificates            20210119                        deb
coreutils                  8.32-4+b1                       deb
[etc...]
```

To generate an SBOM in spdx-json format to a file called `nginx-image-spdx.json` for the nginx container image:

```shell
docker sbom nginx --format spdx-json -o nginx-image-spdx.json
```

See [Announcing Docker SBOM](https://www.docker.com/blog/announcing-docker-sbom-a-step-towards-more-visibility-into-docker-images/) for more details.
