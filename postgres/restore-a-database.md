# Restore A Database

`pg_restore` restores a PostgreSQL database from an archive file created by `pg_dump` in one of the non-plain-text formats.

Restore a database from the file system using `pg_restore` with the following command:

```
pg_restore --host dbserver --port 5432 --data-only --username "postgres" --dbname "orbiks" --role "dbsvcrole" --password "b@dpassword1" --verbose "./backups/orbiks.dump"
```

Short form example with a clean and restore of schema and tables:

```
pg_restore --dbname orbiks --clean "orbiks.dump"
```

The above will restore the schema and data.

### Useful options for the restore process

- To restore data only use the option `--data-only`
- To restore a specific table add the option `--table=tablename` (multiple tables can be selected by writing multiple --table switches)
- To improve restore performance use multiple concurrent jobs with `--jobs=number-of-jobs` where the number of jobs matches the number of CPU cores on the server

### After the restore

Optimise and reclaim fragmented tablespaces by running the `VACUUM ANALYZE` command.

### Passwords and the restore process

- The `--no-password` option requires the existence of a `.pgpass` file. This option can be useful in batch jobs and scripts where no user is present to enter a password.
- The `--password` option is not required as the sever will prompt for a password if the server requires authentication.


See [pg_restore](https://www.postgresql.org/docs/current/app-pgrestore.html) for more details.
