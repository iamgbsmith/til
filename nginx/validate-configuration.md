# Validate Configuration

__Category: Nginx__

You can safely validate Nginx configuration with the following command:

```shell
/usr/bin/nginx -t -c ~/mynginx.conf 
```

The `-t` flag will test for the correct syntax and then try to open files referred in the configuration file with `-c` without permanently running the process. 

This command should be used to validate configuration changes before a restart of Nginx.
