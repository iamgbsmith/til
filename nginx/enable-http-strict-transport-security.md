# Enable HTTP Strict Transport Security

__Category: NGINX__

HTTP Strict Transport Security (HSTS) is a web security policy mechanism that helps to protect websites against Man-In-The-Middle (MITM) attacks such as protocol downgrade attacks and cookie hijacking. It should be enabled on all production sites. 

HSTS can be enabled at either the `http` block for all virtual servers handled by an Nginx instnace or a `server` block for a specific virtual server context.

### Enable at the HTTP block

This will apply to all virtual servers.

```
http {

    # Basic Settings
    tcp_nopush on;
    tcp_nodelay on;
    types_hash_max_size 2048;

    server_tokens off;

    [etc...]

    # Add HSTS header
    add_header Strict-Transport-Security "max-age=31536000; includeSubdomains;" always;

    [etc...]
}
```

### Enable at the virtual server block

This will apply to a specific virtual server.

```
server
{
    listen 443 ssl;

    [etc...]

    # Add perfect forward secrecy
    ssl_prefer_server_ciphers on;

    # Add HSTS header
    add_header Strict-Transport-Security "max-age=31536000; includeSubdomains" always;

    [etc...]
}
```

When a browser sees this header from an HTTPS website it learns that the domain must only be accessed using HTTPS (SSL or TLS) and caches this information for the max-age period for 31,536,000 seconds (approximately 1 year).

The optional includeSubDomains parameter tells the browser that the HSTS policy also applies to all subdomains of the current domain.

See https://www.nginx.com/blog/http-strict-transport-security-hsts-and-nginx/
