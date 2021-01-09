# Get The Current User

__Category: Postgres__

Connections in Postgres are established using an account which can spawn sessions to run DDL or DML queries. 

To obtain the name of the application which has established a session with Postgres, run the following command:

```sql
> SHOW application_name;
 application_name
------------------
 pgAdmin 4 - CONN:2952973
```

When DDL or DML is run, details of the application which has spawned the query can also be otained from `pg_stat_activity`.

See [Postgres monitoring stats docs](https://www.postgresql.org/docs/current/monitoring-stats.html#MONITORING-STATS-VIEWS) for more details.
