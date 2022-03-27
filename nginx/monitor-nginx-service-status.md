# Monitor Nginx Service Status

__Category: Nginx__

You can monitor Nginx service status using the `stub-status` module. This will show the total request count across all sites and the total number of connections.

```shell
server {  

  # Configuration...

  location / {
    allow 		    all;
    add_header    X-Version 1.2.0; 
  }

  location /serverstatus {      
    stub_status   on;
    access_log    vhost;
    allow 		    127.0.01;
    add_header 	  X-Version 1.2.0; 
    deny all;
    auth_basic    "Server Status";
    auth_basic_user_file conf/nginxstaus;
  }

  # More configuration...

}
```

The above status endpoint can be accessed locally at https://127.0.01/serverstatus when the user enters HTTP Basic Auth credentials in the file `conf/nginxstaus`.

Sample output:

```shell
Active connections: 20 
server accepts handled requests
 8658 8984 40223
Reading: 1 Writing: 1 Waiting: 15
```

This sample output shows that 8658 connections were accepted, 8984 connections were handled, and 40223 requests were processed (spanning all HTTP response codes).

See [Nginx Stub Status Module](https://nginx.org/en/docs/http/ngx_http_stub_status_module.html) for more details.
