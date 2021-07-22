# Curl Showing HTTP Headers

The `curl` command can either display headers in the console or write the header output from an HTTP response to file.

Display headers in the console using the `-v` flag:

```shell
curl -v https://www.google.com
```

Write headers to an external file using the `-D` flag:

```shell
curl -D http-headers.txt 'https://cms-assets.tutsplus.com/uploads/users/30/posts/23880/image/download-attribute-caniuse.png' > image.png
```

Show the header output from the previous command:

```
cat http-headers.txt
```
