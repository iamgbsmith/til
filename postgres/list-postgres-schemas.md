# List Postgres Schemas

__Category: Postgres__

Postgres refers to schemas as namespaces. By default, you will be working with the `public` schema.

To obtain a list of schemas, run the following query:

```sql
SELECT * FROM pg_namespace;
```
