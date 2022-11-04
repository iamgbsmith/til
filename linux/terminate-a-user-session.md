# Terminate A User Session

__Category: Linux__

You can terminate a user session based on a username or session ID. This will require using root or sudo privileges.

### Terminate all sessions for a specific user

Assume the username is `bilbo`, terminate all sessions with the following command:

```shell
killall -u bilbo
```

### Terminate a specific session

List all sessions using the `w` command to identify logged in users.

Sample output:

```shell
jack@orbiks:~ $ w
 20:03:59 up 9 min,  2 users,  load average: 0.16, 0.23, 0.14
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
billy       pts/0    192.168.68.61    19:54    3:13   0.26s  0.26s -bash
jana        pts/1    192.168.68.61    19:59    0.00s  0.22s  0.03s w
```

Termimate the session for user `jana` by matching on the TTY column value:

```shell
pkill -9 -t pts/1
```
