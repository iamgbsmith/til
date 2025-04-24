# Get Process ID By Name

__Category: Mac__

You can get the PID for a running process by name. 

For example, to get the PID for Google Chrome use the following:

```shell
ps -A | grep -m1 chrome | awk '{print $1}'
```

The same command will also work on Linux.
