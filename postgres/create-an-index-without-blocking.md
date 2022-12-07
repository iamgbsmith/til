# Create An Index Without Blocking

__Category: Postgres__

Indexes can be created in Postgres without holding a lock on a table.

```sql
CREATE INDEX CONCURRENTLY tablename_columnname_idx ON tablename (columnname);
```

This operation can not be performed inside a transaction.
