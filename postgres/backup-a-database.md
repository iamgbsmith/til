# Backup A Database

__Category: Postgres__

`pg_dump` extracts a single PostgreSQL database into a script or archive file.

Extract a database to the file system using `pg_dump` with the following command:

```
pg_dump -Fc orbiks --file="./backups/orbiks.dump"
```

The above will dump the schema and data for a database called "orbiks" into an archive file format.

### Useful options for the backup process

* To backup data only, use the option `--data-only`
* To backup schema only, use the option `--schema-only`
* To specify plain text output, use file format of plain with `-Fp`
* To backup a specific table, add the option `--table=tablename` (multiple tables can be selected by writing multiple --table switches) 
* To reduce the time it takes to backup, use multiple concurrent jobs with `--jobs=number-of-jobs` where the number of jobs matches the number of CPU cores on the server (this will increase load on the server and only works with the directory option `-Fd`)
* To compress the backup, specify a compression level using `--compress=0..9` where 0 means none and 9 is maximum (default compression level is moderate)

__Note:__ pg_dump only dumps a single database. To back up an entire cluster, or to back up global objects that are common to all databases in a cluster (such as roles and tablespaces), use pg_dumpall.

See [pg_dump](https://www.postgresql.org/docs/current/app-pgdump.html) for more details.

