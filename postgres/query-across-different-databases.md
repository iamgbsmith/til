# Query Across Different Databases

__Category: Postgres__

Postgres supports the ability to execute queries which join results against a query run on another local or remote database using the `dblink` module. 

You might need to query across databases if you are performing a data migration or developing a multi-tenant SaaS solution which shards data.

### Install the dblink module

```sql
CREATE EXTENSION IF NOT EXISTS "dblink";
```

### Execute the query

Assume there are two databases; the one you are currently working from, and another database called `user_registry`.

Note the use of `SELECT * FROM dblink` in the statement below.

```sql
SELECT orders.part_number, orders.description, users.id, users.first_name, users.last_name 
FROM orders
LEFT JOIN (
	SELECT * 
	FROM dblink('dbname=user_registry', 'SELECT id, first_name, last_name FROM users')
	AS users(id uuid, first_name varchar(64), last_name varchar(64))
) users on users.id = orders.user_id
WHERE users.id = 'f9684dd7-0f9d-472d-92bc-ade3361a066c';
```

For a remote database which requires credentials you will need to specify them in the select statement as follows:

```sql
SELECT * 
FROM dblink('dbname=remotedb port=5432 host=remoteserver user=someuser password=b@dpa55w0rd',
          'SELECT id, first_name, last_name FROM users')
AS ...
```

__Note:__ In the above statement, the credentials are hard-coded for illustrative purposes. Do not use hard-coded, plain-text credentials. Specify them as variables.

See [PostgreSQL dblink](https://www.postgresql.org/docs/14/contrib-dblink-function.html) for more details.



