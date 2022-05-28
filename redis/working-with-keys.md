# Working With Keys

__Category: Redis__

You can query Redis for information related to objects stored in the keyspace. 

Start the Redis command line interface:

```shell
redis-cli
```

Count the number of keys using `DBSIZE`:

```shell
127.0.0.1:6379> DBSIZE
(integer) 371
```

List key information using `INFO keyspace`:

```shell
127.0.0.1:6379> INFO keyspace
# Keyspace
db0:keys=371,expires=371,avg_ttl=197287879
```

Set a value for a key:

```shell
127.0.0.1:6379> SET some-key "Some random string"
```

Find keys which match a specific wildcard pattern, for example, containing the string `uname_to_access`:

```shell
127.0.0.1:6379> KEYS *uname_to_access:*
1) "user-profile:uname_to_access:orbiks-mobile-app:maryh"
2) "user-profile:uname_to_access:orbiks-mobile-app:seanl"
3) "user-profile:uname_to_access:orbiks-mobile-app:fredq"
```

__Note: KEYS is a command that should only be used in production environments with extreme care. It may seriously impact Redis server performance if run without a search filter against large databases.__

Show whether a key exists:

```shell
127.0.0.1:6379> EXISTS some-key
```

Show the value for a key using the Redis-specific encoded format.

```shell
127.0.0.1:6379> DUMP some-key
```

Delete a key:

```shell
127.0.0.1:6379> DEL some-key
```

See [Redis KEYS pattern](https://redis.io/commands/keys) for more details.
