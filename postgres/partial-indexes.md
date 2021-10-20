# Partial Indexes

__Category: Postgres__

A partial index is an index built over a subset of a table. Partial indexes allow you to create indexes with a predicate (filter / where clause) defined by a conditional expression, and they are typically smaller resulting in faster reads and writes.

For example, to create a partial index include a `WHERE` clause in the index creation statement:

```sql
CREATE INDEX my_index ON my_table (index_column) WHERE filter_column IS TRUE;
```

The advantage of this over an index on both index_column and filter_column such as the following:

```sql
CREATE INDEX my_index ON my_table (index_column, filter_column);
```

...is that only those rows that match the predicate are indexed.

__Note:__ To ensure optimal performance, partial indexes should only be created when the predicate filters out a large percentage of records.
