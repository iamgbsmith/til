# Export From A Table Or Query To CSV

__Category: Postgres__

You can export data from a table or query to a CSV file using the `COPY` command. Data will be transferred from the Postgres host to the machine the command is being run on.

Copy all data from a table called `employees`:

```sql
COPY employees TO '/path/to/file/employees_data.csv';
```

Copy columns from a SELECT statement into a compressed file by piping the output through an external compression program:

```sql
COPY (SELECT first_name, last_name, start_date, email FROM employees) TO PROGRAM 'zip > /path/to/file/employees_data.zip';
```

You must have permission to write the output from the COPY command to the local filesystem.

See [Postgres COPY](https://www.postgresql.org/docs/current/sql-copy.html) for more details.
