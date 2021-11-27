# Schedule Jobs With Crontab

__Category: Linux__

`crontab` can be used to schedule and run tasks at regular intervals. 

Create a new crontab (if one doesn't already exist):

```shell
crontab -e
```

Entries should follow the format:

```shell
*    *    *   *   *    command-to-execute
|    |    |   |   |
|    |    |   |   +----- day of week (0 - 6) (Sunday=0)
|    |    |   +------- month (1 - 12)
|    |    +--------- day of month (1 - 31)
|    +----------- hour (0 - 23)
+------------- min (0 - 59)
```

For example, run a shell script command every 45 minutes:

```shell
*/45 * * * * bash /data/check-mail.sh
```

Run a shell script every day at 2:30pm:

```shell
30 14 * * * bash /data/backup-files.sh
```

List crontab entries:

```shell
crontab -l
```

__Note:__ You can setup `crontab` to run using the same syntax on macOS.
