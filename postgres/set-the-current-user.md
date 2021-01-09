# Set The Current User

__Category: Postgres__

Connections in Postgres are established using an account which can spawn sessions to run DDL or DML queries. 

To set the the name of the application which has established a session with Postgres, run the following command:

```sql
> SET application_name = 'my_application';
```

Once set, the name will be reflected in `pg_stat_activity` for the duration of the session until it is changed.
