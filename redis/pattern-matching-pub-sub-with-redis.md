# Pattern Matching Pub Sub With Redis

__Category: Redis__

Redis supports pattern matching pub/sub channels. Clients may subscribe to glob-style patterns in order to receive all the messages sent to channel names matching a given pattern.

### Subscribe using pattern matching 

Assume you want to subscribe to any messages starting with "orders". Issue the following command using the Redis CLI:

```shell
127.0.0.1:6379> PSUBSCRIBE orders.*
```

The client will receive messages published to `orders.stores.auckland`, `orders.stores.wellington` and `orders.takeaways.christchurch`.

### Unsubscribe from a channel

To unsubscribe, issue the following command:

```shell
127.0.0.1:6379> PUNSUBSCRIBE orders.*
```

If no name is provided, the client will unsubscribe from all channels.

### Channl and pattern matching subscriptions

A client may receive a single message more than once if it is subscribed to a channel and a pattern.

Assume a subscription as follows:

```shell
127.0.0.1:6379> SUBSCRIBE logins
127.0.0.1:6379> PSUBSCRIBE log*
```

The client will receive messages published to `logins` and `logouts`.
