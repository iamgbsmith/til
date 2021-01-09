# Determine Index Hit Rate

__Category: Postgres__

Postgres indexes should be tuned to ensure the highest chance of acheiving a direct hit. Hitting an in-memory index is manifestly faster than having to perform a sequential scan across a spinning disk.

### Index effectiveness for all user created tables in all schemas

```sql
SELECT 
  schemaname schema_name,
  relname table_name, 
  n_live_tup,
  100 * idx_scan / (seq_scan + idx_scan) index_hit_rate
FROM 
  pg_stat_user_tables
WHERE 
  seq_scan + idx_scan > 0 
ORDER BY 
  n_live_tup DESC;
```

Ideally, the index hit rate should be as close as possible to 100 for tables with thousands of rows. If not, this indicates an index should be considered based on the types of queries that are performed.

### Index effectiveness for a specific user created table

In the `WHERE` clause, specify the value for `relname` as the name of the table.

```sql
SELECT 
  schemaname schema_name,
  relname table_name, 
  n_live_tup,
  100 * idx_scan / (seq_scan + idx_scan) index_hit_rate
FROM 
  pg_stat_user_tables
WHERE 
  seq_scan + idx_scan > 0 
AND
  relname = 'some_table'
ORDER BY 
  n_live_tup DESC;
```

__Caveat:__ For tables with a small number of rows, the index hit rate may be low, or zero, because Postgres sometimes defaults to performing a sequential scan.

### What does n_live_tup represent? 

The value for `n_live_tup` is the number of "live" rows in the table as captured by the statistics collector. Individual database backends send information to the statistics collector over a UDP socket asynchronously when a database operation has finished. Due to this, there can be a difference between the physical number of rows in the database obtained using `SELECT count(*) FROM table_name` and what is stored in `pg_stat_user_tables`.



