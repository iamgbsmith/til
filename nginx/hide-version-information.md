# Hide Version Information

__Category: Nginx__

It is good security practice to remove web server version information by modifying the HTTP response header. Obfuscating details will help prevent bad actors from using known exploits for specific versions of a web server that could be vulnerable to attack. 

To prevent Nginx version information being display in HTTP Response headers edit the configuration file `/etc/nginx/nginx.conf` to disable server tokens. 

Under the HTTP Options and ## lines, add a new line: 

```shell
server_tokens off;
```

Save changes and restart Nginx.

Validate the Nginx server version is not displayed:

```shell
curl --head www.yourdomain.com
```

Output:

```shell
HTTP/2 204 
date: Sun, 21 Feb 2021 21:28:40 GMT
server: nginx
etag: W/"a-bAsFyilMr4Ra1hIU5PyoyFRunpI"
strict-transport-security: max-age=31536000; includeSubdomains; preload
x-content-type-options: nosniff
x-frame-options: DENY
x-xss-protection: 1; mode=block
referrer-policy: same-origin
```

See [OWASP WSTG-INFO-02 Fingerprint Web Server](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/01-Information_Gathering/02-Fingerprint_Web_Server) for more details.