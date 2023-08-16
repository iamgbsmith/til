# Connect With Redis Auth

__Category: Redis__

If security is configured on a Redis instance you will be asked to authenticate with a username and password when performing commands using `redis-cli`. For example, the following command required authentication on a secured server:

```shell
127.0.0.1:6379> INFO server
NOAUTH Authentication required.
```

Authenticate with the following command:

```shell
AUTH someusername somerandompassword
```
__Note:__ The value for username is optional.
