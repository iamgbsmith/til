# Revoke Privileges From A User Or Role

__Category: Postgres__

This TIL shows how to revoke privileges from a user or role.

### Revoke privileges from a user

Revoke use of the default schema `public` for the user `orbiks_dbusr`:

```sql
REVOKE USAGE ON SCHEMA public FROM orbiks_dbusr;
```

Revoke all permissions on a set of tables for the user `orbiks_dbusr`:

```sql
REVOKE ALL ON orders, events, alerts IN SCHEMA public FROM orbiks_dbusr;
```

Revoke specific permissions on a set of tables for the user `orbiks_dbusr`:

```sql
REVOKE DELETE, UPDATE ON orders, events, alerts IN SCHEMA public FROM orbiks_dbusr;
```

See [PostgreSQL REVOKE](https://www.postgresql.org/docs/current/sql-revoke.html) for more details.
