# List Database Users

List users in a Postgres database from the `psql` interface using the `\du` command:

```sql
postgres=# \du
                                   List of roles
 Role name |                         Attributes                         | Member of 
-----------+------------------------------------------------------------+-----------
 joebloggs | Superuser, Create role, Create DB                          | {}
 someapp   | Create DB, Replication                                     | {}
 postgres  | Superuser, Create role, Create DB, Replication, Bypass RLS | {}
```

Alternatively, issue the following SQL command:

```sql
select usesysid as user_id,
       usename as username,
       usesuper as is_superuser,
       valuntil as password_expiration
from pg_shadow
order by usename;
```

Output:

```sql
 user_id | username  | is_superuser | password_expiration 
---------+-----------+--------------+---------------------
   16384 | joebloggs | t            | 
    3221 | someapp   | f            | 
      10 | postgres  | t            | 
```