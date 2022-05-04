# Hash Join Versus Merge Join

__Category: Postgres__

A query in Postgres that joins only one row from one table and associated rows from another table will use a Nested Loop Join.

When joining tables with many rows on either side of the query, the query planner will use a Hash or Merge Join if the join condition allows for it.

### Hash Join

Hash Joins do not require sorting and instead create a hash of the inner (smaller) table and then scan for matches in the outer (larger) table.

Hash Joins are preferred if the resulting hash table can fit into `work_mem`.

### Merge Join

Merge Joins are used to merge two tables and require both tables to be sorted. The query planner will sort both tables then read rows sequentially. 

Merge Joins are usually faster than Hash Joins but can have a significantly higher cost if Postgres needs perform an external sort to disk as part of query execution.

### Disable join strategies

To see how the performance differs between join strategies, you can disable either in the current session before running your query:

```sql
SET enable_hashjoin = off;
```

Or: 

```sql
SET enable_mergejoin = off;
```

By default, these join strategies are __enabled.__
