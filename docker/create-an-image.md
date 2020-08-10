# Create An Image

With a Dockerfile you can create a Docker image using the following command:

```shell
docker build -t orbiks/web-container:0.4.7 .
```

In the above example:

* `-t` means name and tag using the 'name:tag' format
* `.` means use the Dockerfile from the current directory
* The name of the image is `orbiks/web-container` and the version is `0.4.7`
