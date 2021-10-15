# Show Installed Extensions

__Category: Postgres__

You can list the extensions that are installed for Postgres database using the `\dx` command in psql:

```shell
my_database=# \dx;

List of installed extensions
-[ RECORD 1 ]------------------------------------------------
Name        | plpgsql
Version     | 1.0
Schema      | pg_catalog
Description | PL/pgSQL procedural language
-[ RECORD 2 ]------------------------------------------------
Name        | uuid-ossp
Version     | 1.1
Schema      | public
Description | generate universally unique identifiers (UUIDs)
```
