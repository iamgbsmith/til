# Improve Website Performance Using GZIP

__Category: Nginx__

Compressing responses using gzip can improve website performance by significantly reducing the size of data transferred by Nginx. 

To enable gzip compression on all content which matches configuration settings, add the following to /etc/nginx/nginx.conf within the the `http {` block.
 
```code
  ##
  # Gzip Settings
  ##
  gzip on;

  # Enable compression HTTP/1.1
  gzip_http_version 1.1;
  
  # Compression level (1-9)
  gzip_comp_level 5;

  # Minimum length of content to compress with gzip
  gzip_min_length 1000;

  # Instruct proxies to cache both the gzipped and regular version of a resource
  # whenever the client's Accept-Encoding capabilities header varies
  gzip_vary on;

  # Compress data even for clients that are connecting via proxies
  gzip_proxied no-cache no-store private expired auth;

  gzip_buffers 16 8k;
  
  # Compress all output labeled with one of the following MIME types
  gzip_types
    application/atom+xml
    application/javascript
    application/json
    application/rss+xml
    application/vnd.ms-fontobject
    application/x-font-ttf
    application/x-web-app-manifest+json
    application/xhtml+xml
    application/xml
    application/xml+rss 
    font/opentype
    image/svg+xml
    image/x-icon
    text/css
    text/plain
    text/x-component
    text/xml
    text/javascript;
  # text/html is always compressed by HttpGzipModule
```

Save changes and restart Nginx.

You can test Nginx is serving content using gzip as follows:

```shell
curl -H "Accept-Encoding: gzip" -I http://localhost/index.html
```

The response should include `Content-Encoding: gzip` in the output:

```shell
HTTP/1.1 200 OK
Server: nginx/1.21.3 (Ubuntu)
Date: Mon, 25 Oct 2021 10:15:31 GMT
Content-Type: text/html
Last-Modified: Mon, 25 Oct 2021 10:15:31 GMT
Connection: keep-alive
ETag: W/"43252da3a-320"
Content-Encoding: gzip
```

__Note:__ Compression occurs at runtime and can add processing overhead. Using a gzip compression level of 5 strikes a balance between size and CPU use, offering about 75% reduction for most ASCII files.
