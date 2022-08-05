# Enable Row Level Security

__Category: Postgres__

Postgres Row Level Security (RLS) is an approach which can be used for data isolation in a multi-tenant context. Enabling RLS will restrict read and write actions so that tenants can only access their rows. 

This TIL assumes you have installed the  `uuid-ossp` extension. Tables will be partioned using a Tenant UUID column called `tenant_id` and this column will exist in every table that requires support for multi-tenancy.

Assume you have a table called `tenant` with a version 4 UUID as the primary key:

```sql
CREATE TABLE IF NOT EXISTS tenant (
    tenant_id uuid DEFAULT uuid_generate_v4() PRIMARY KEY,
    created_date timestamp(3) WITH TIME ZONE DEFAULT now(),
    name varchar(256) NOT NULL UNIQUE,
    status varchar(64) CHECK (status IN ('active', 'suspended', 'disabled')),
    tier varchar(64) CHECK (tier IN ('bronze', 'silver', 'gold', 'platinum', 'custom')) 
);
```

Tenants will have users:

```sql
CREATE TABLE IF NOT EXISTS tenant_user (
    user_id uuid DEFAULT uuid_generate_v4() PRIMARY KEY,
    tenant_id uuid NOT NULL REFERENCES tenant (tenant_id) ON DELETE RESTRICT,
    created_date timestamp(3) WITH TIME ZONE DEFAULT now(),
    email varchar(128) NOT NULL UNIQUE,
    first_name varchar(128) NOT NULL CHECK (first_name <> ''),
    last_name varchar(128) NOT NULL CHECK (last_name <> '')
);
```

__When using database connection pooling, connections are established using a generic database user that has specifically created for the application. The value used for enforcing RLS (in this example `app.current_tenant_id`) must be set prior to the execution of each SQL query.__

Enable RLS for the `tenant` table:

```sql
ALTER TABLE tenant ENABLE ROW LEVEL SECURITY;
CREATE POLICY tenant_isolation_policy ON tenant
USING (tenant_id = current_setting('app.current_tenant_id')::UUID);
```

Enable RLS for the `tenant_user` table:

```sql
ALTER TABLE tenant_user ENABLE ROW LEVEL SECURITY;
CREATE POLICY tenant_user_isolation_policy ON tenant_user
USING (tenant_id = current_setting('app.current_tenant_id')::UUID);
```

When queries are run, the value of `app.current_tenent_id` will be used to only return rows which match the tenant ID. If the value for `app.current_tenent_id` is not specified prior to running the query, it will fail securely. This value should be set and cleared by the database connection pooling framework before and after each query is run.

__Note:__ Postgres admin users and any role created with the `BYPASSRLS` attribute are not subject to table RLS policies.
