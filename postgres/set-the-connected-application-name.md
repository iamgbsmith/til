# Set The Connected Application Name

__Category: Postgres__

To set the the name of the application which has established a connection to Postgres, run the following command:

```sql
SET application_name = 'orbiks';
```

Once set, the name will be reflected in `pg_stat_activity` for the duration of the session until it is changed.
