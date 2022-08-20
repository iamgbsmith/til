# Basic Pub Sub With Redis

__Category: Redis__

Aysnchronous messaging between a publisher and subscribers improves application scalability, resilience, and supports use of a dynamic network topology. Redis supports this messaging pattern using pub/sub channels.

### Subscribe to a channel

Assume you want to subscribe to two channels called "purchases" and "registrations". Issue the following command using the Redis CLI:

```shell
127.0.0.1:6379> SUBSCRIBE purchases registrations
```

Another client can publish a message to either of these channels. In this example, we will notify subscribers to the "registrations" channel that a user with the email address `buddy.guy@jazzclub.com` registered for using a hypothetical system. 

```shell
127.0.0.1:6379> PUBLISH registrations buddy.guy@jazzclub.com
```

### Unsubscribe from a channel

To unsubscribe from a channel, issue the following command:

```shell
127.0.0.1:6379> UNSUBSCRIBE purchases registrations
```

If no channel names are provided, the client will unsubscribe from all channels.

__Note:__ Pub/Sub has no relation to the database key space. Scoping can be achieved using a prefix for the channel name.
