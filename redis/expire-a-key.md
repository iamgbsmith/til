# Expire A Key

__Category: Redis__

Redis keys are normally created without an associated time-to-live.

You can expire a key either based on specific datetime or a timeout duration after it has been added to a Redis database.

Start the Redis command line interface:

```shell
redis-cli
```

Assume you have set a key value:

```shell
127.0.0.1:6379> SET some-key "Some random string"
```

Expire a key after 10 minutes:

```shell
127.0.0.1:6379> EXPIRE some-key 10
```

Expire a key at a specific time (uses Unix timestamp format). For example, to expire a key at 8:30pm GMT on May 1, 2025:

```shell
127.0.0.1:6379> EXPIREAT some-key 1746131400
```

Show the time-to-live for a key:

```shell
127.0.0.1:6379> TTL some-key
```

Clear a timeout for a key, turning it back into a persistent key:

```shell
127.0.0.1:6379> PERSIST some-key
```

__Note: Key expiry commands return an integer value of 1 indicating timeout is set and 0 if a timeout could not be set or the key does not exist.__

See [Redis EXPIRE key seconds](https://redis.io/commands/expire) for more details.
