# Get Server Info

__Category: Redis__

Details about a Redis server including version and uptime can be obtained using the `INFO server` command. 

Start the Redis command line interface:

```shell
redis-cli
```

Query the Redis server:

```shell
127.0.0.1:6379> INFO server
# Server
redis_version:5.0.3
redis_git_sha1:00000000
redis_git_dirty:0
redis_build_id:35c602fe923674ab
redis_mode:standalone
os:Linux 4.15.0-1031-aws x86_64
arch_bits:64
multiplexing_api:epoll
atomicvar_api:atomic-builtin
gcc_version:6.4.0
process_id:6
run_id:92c217c459be0c73c4f3be77911d1d76bffce8a6
tcp_port:6379
uptime_in_seconds:5517758
uptime_in_days:63
hz:10
configured_hz:10
lru_clock:8664771
executable:/data/redis-server
config_file:
```

See [The INFO command](https://redis.io/commands/info) for more details.
