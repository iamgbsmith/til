# Measure Redis Latency

__Category: Redis__

Clients connect to Redis using a TCP/IP connection or a Unix domain connection. Connection latency depends on the network and system hardware.

You can measure Redis latency rom the command line with redis-cli.

### Measure intrinsic latency

Intrinsic latency is the latency that relates to the environment where Redis is run. It should be measured locally. 

To run tests for 100 seconds:

```shell
redis-cli --intrinsic-latency 100
```

Saample output:

```shell
Max latency so far: 1 microseconds.
Max latency so far: 7 microseconds.
Max latency so far: 18 microseconds.
Max latency so far: 410 microseconds.
Max latency so far: 466 microseconds.
Max latency so far: 1770 microseconds.
Max latency so far: 2677 microseconds.
Max latency so far: 3710 microseconds.
Max latency so far: 6570 microseconds.
Max latency so far: 10268 microseconds.
Max latency so far: 13260 microseconds.

2451994130 total runs (avg latency: 0.0408 microseconds / 40.78 nanoseconds per run).
Worst run took 325134x longer than the average latency.
```

The above output was generated on Redis running within a Docker container. It shows a maximum latency of 13.26 milliseconds.

### Measure Remote Latency

To measure remote latency, specify a host and port for the remote server:

```shell
redis-cli --latency -h redis.orbiks.net -p 6379
```

See [Diagnosing latency issues](https://redis.io/docs/reference/optimization/latency) for more details.