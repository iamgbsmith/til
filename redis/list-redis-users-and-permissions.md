# List Redis Users And Permissions

__Category: Redis__

You can list users and permissions which have been configured in the Redis auth file with the `ACL LIST` command:

```shell
127.0.0.1:6379> ACL LIST
```

Sample output:

```shell
1) "user default on #ab5429cbd11bc87c624afed79d02dc839c8195084a0af64dc059e4627fd15d2 ~* 8* +@all"
```

To temporarily set a password for the default user until a Redis server restart, enter the following command:

```shell
127.0.0.1:6379> CONFIG SET requirepass "mypass"
```
