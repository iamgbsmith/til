# Configure Data Snapshotting

__Category: Redis__

Default configuration in Redis saves snapshots of the dataset on disk to a binary file called `dump.rdb`.

RDB (Redis Database) persistence uses snapshots (point-in-time representations) of the entire dataset. Whilst snapshot settings can be modified at run time, you should configure snapshot settings at build/deployment time.

You can configure Redis to save the dataset every N seconds if there are at least M changes in the dataset.

Edit the file `/etc/redis/redis.conf` to set the required values. For example:

```
################################ SNAPSHOTTING  ################################
#
# Save the DB on disk:
#
#   save <seconds> <changes>
#
#   Save the DB if both the given number of seconds and the given
#   number of write operations against the DB occurred.
#
#   In the example below the behaviour will be to save:
#
#   after 900 sec (15 min) if at least 1 key changed
#   after 300 sec (5 min) if at least 10 keys changed
#   after 60 sec if at least 10000 keys changed
#   after 10 sec if at least 50000 keys changed

save 900 1
save 300 10
save 60 10000
save 10 50000
```

__Note:__  Your Recovery Point Objective for data stored in Redis will determine which Redis persistence mode to use, snapshot configuration, and whether you need to combine the RDB and AOF modes for maximum durability.

See [Redis persistence](https://redis.io/topics/persistence) for more details.
