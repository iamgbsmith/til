# Grant Privileges To A User Or Role

__Category: Postgres__

For security reasons you should create a user with the least amount of privilege required for your application to connect to a Postgres database.

This TIL shows how to grant privileges to a user or role which restricts rights so that it cannot not be used to create new users, database objects, or drop tables, schemas, or databases.

### Grant privileges to a user

Grant use of the default schema `public` for the user `orbiks_dbusr`:

```sql
GRANT USAGE ON SCHEMA public TO orbiks_dbusr;
```

Grant access to all tables in the schema `public` for the user `orbiks_dbusr`:

```sql
GRANT SELECT, INSERT, DELETE, UPDATE ON ALL TABLES IN SCHEMA public TO orbiks_dbusr;
```

Grant specific permissions on a set of tables for the user `orbiks_dbusr`:

```sql
GRANT SELECT, INSERT ON orders, events, alerts IN SCHEMA public TO orbiks_dbusr;
```

See [PostgreSQL GRANT](https://www.postgresql.org/docs/current/sql-grant.html) for more details.
