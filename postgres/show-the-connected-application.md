# Show The Connected Application

__Category: Postgres__

Connections in Postgres are established using an account which can spawn sessions to run DDL or DML queries. 

To obtain the name of the application which has established a connection with Postgres, run the following command:

```sql
SHOW application_name;
```

Output:

```
 application_name
------------------
 pgAdmin 4 - CONN:2952973
```
