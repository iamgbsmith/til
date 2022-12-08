# Terminate All Queries For A User

__Category: Postgres__

Rogue queries being run by a specific user can be terminated.

```sql
WITH pids AS (
  SELECT pid
  FROM pg_stat_activity
  WHERE username='foobar'
)
SELECT pg_cancel_backend(pid);  
FROM pids;
```

This operation can take time to run, and in some situations, is not guaranteed to work.
