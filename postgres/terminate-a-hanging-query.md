# Terminate A Hanging Query

__Category: Postgres__

Long running queries in Postgres can affect database performance and cause application bottlenecks. Typically, these types of queries are poorly written, untuned, and work across large datasets.

To determine how long active queries have been running Postgres, execute the following command:

```sql
SELECT now() - pg_stat_activity.query_start AS duration, * FROM pg_stat_activity WHERE state = 'active';
```

If the value for the duration is more than a few minutes, it is likely the query will be causing database performance problems. 

Using the PID from the above query results, terminate the query using the following command which leaves the connection open upon completion:

```sql
SELECT pg_cancel_backend(PID);
```

This operation can take time to run, and in some situations, may not work. A more forceful, but riskier way to kill the query is to execute the following:

```sql
SELECT pg_terminate_backend(PID);
```

__WARNING__

Using the `pg_terminate_backend` command will terminate the query and connection which can lead to a full database restart to ensure consistency.