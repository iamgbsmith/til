# Improve Query Planner Performance

__Category: Postgres__

You can improve Postgres query planner performance and influence plans chosen by the query optimiser by  increasing the value of the `default_statistics_target` configuration parameter.

The `default_statistics_target` determines the amount of information from a table that is captured by an ANALYZE. Increasing this value can result in:

* Better statistics for distributed data.
* Better query plans as the planner has more accurate statistics for a table. 
* Faster query execution due to better query plans being available.

### Default statistics example configuration

Assuming a table called "orders" with a column called "transaction_date", use the following SQL query to configure statistics:

```sql
ALTER TABLE orders ALTER COLUMN transaction_date SET STATISTICS 1000;
```

Run the analyze command:

```sql
ANALYZE orders;
```

You can set this value for all tables by configuring the `default_statistics_target` property in `postgres.conf`.

### Tradeoffs 

Increasing this value allows for more accurate planner estimates to be made, particularly for large tables or irregular data distributions, at the cost of consuming more space in `pg_statistic` and taking fractionally time to compute the estimates with a higher CPU load. Always benchmark your queries before and after to understand their performance characteristics.

__Note:__ Most applications use a default value of 100. For small or simple databases a value of 10 or 50 may suffice. High transaction systems or data warehouse applications should generally use a value of 500 to 1000. Always increase statistics targets on a per column basis.
