# NGINX Network Resolver

__Category: Docker__

NGINX reverse proxy entries using the `location` directive can return a bad gateway error if the upstream server is restarted. The solution to this is to use the Docker DNS server at `127.0.0.11` and disable IPv6 (AAAA record) for DNS queries.

```
location /orbiks/upstream-server {
      # Use internal Docker DNS and cache for 30s
      resolver 127.0.0.11 valid=30s ipv6=off;

      set $upstream     http://anotherserver/upstream-server;
      proxy_pass        $upstream;
      ...
}
```
