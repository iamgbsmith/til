# Log Slow Redis Queries

__Category: Redis__

In Redis 6.0 or higher, you can log slow queries in Redis by setting a "slowlog" execution time threshold (execution time does not include I/O operations such as communicating with the client or sending the reply). Slow queries will be logged to memory. 

Edit your `redis.conf` to set the value (in microseconds). The default is 10000 microseconds. Alternatively, you can change the value while the server is running using the `CONFIG GET` and `CONFIG SET` commands. 

To log queries which take longer than 100000 microseconds (0.1 seconds):

```shell
CONFIG SET slowlog-log-slower-than 100000
```

The maximum number of entries in the slow log is governed by the `slowlog-max-len` configuration setting.

Use the following Redis command to get slow queries:

```shell
SLOWLOG GET [count]
```

By default, the above command returns the latest 10 entries in the log. 

To show the length of the slow log:

```shell
SLOWLOG LEN
```

To reset the slow log:

```shell
SLOWLOG RESET
```
