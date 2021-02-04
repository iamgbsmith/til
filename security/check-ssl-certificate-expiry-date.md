# Check SSL Certificate Expiry Date

__Category: Security__

You can print the expiry date for an SSL certificate from the command line. For example, the following will inspect the SSL certificate for facebook.com:

```shell
echo | openssl s_client -showcerts -connect facebook.com:443 2>/dev/null | openssl x509 -inform pem -noout -dates
```

Output:

```shell
notBefore=Dec 22 00:00:00 2020 GMT
notAfter=Mar 21 23:59:59 2021 GMT
```

The value for `notAfter` is the SSL certificate expiry date.