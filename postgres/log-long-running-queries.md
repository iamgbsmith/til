# Log Long Running Queries

__Category: Postgres__

You can gain more insights into slow system performance on Postgres by logging long running queries. This technique should only be used temporarily while you are trying to debug database performance.

Edit `postgresql.conf` and search for the line which states `#log_min_duration_statement = -1`

Uncomment this line and change the value to the number of milliseconds you want to use as the threshold for logging long running queries.

For example, to log queries which take 15 seconds or longer to execute:

```shell
log_min_duration_statement = 15000
```

Save the file and reload the Postgres configuration without a full restart using: `service postgresql reload`

The log file entries will be written to one of the following directories:

```shell
/var/lib/pgsql/PG_VERSION/data/log/
/var/log/postgresql/
/var/lib/postgresql/PG_VERSION/main/pg_log
```

Confirm the log file location using the following command:

```shell
psql -U postgres -c 'SHOW log_directory'
```

__Note:__ Setting the value for `log_min_duration_statement` to 0 or a small number can generate too much logging information which slows down system performance and increases disk space usage. Ensure you disable logging of long running queries unless absolutely necessary in a production system.