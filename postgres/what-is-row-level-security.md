# What Is Row Level Security

__Category: Postgres__

Row Level Security (RLS) is a Postgres security feature that allows administrators to define policies that restrict which rows in a table are returned by SELECT queries or which rows are affected by INSERT, UPDATE, and DELETE commands.

RLS is used when a database connection tries to perform an action on a table. A filter is applied before the query criteria or filtering, and the data is narrowed or rejected according to the security policy.

RLS is useful when you need to implement partitioning in a multi-tenant SaaS architecture at a database level.

See [PostgreSQL Row Security Policies](https://www.postgresql.org/docs/current/ddl-rowsecurity.html) for more details.
