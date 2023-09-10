# Ignore Invalid SSL Certificates With Curl

__Category: Security__

`curl` may fail to establish a valid connection with any server which has an invalid or expired SSL certificate.

To ignore this use the `--insecure` parameter. For example:

```shell
curl -I --insecure https://www.somerandomdomain.com
```
