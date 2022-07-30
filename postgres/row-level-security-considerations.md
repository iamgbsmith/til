# Row Level Security Considerations

__Category: Postgres__

Row Level Security (RLS) provides multi-tenant data isolation for a Postgres database. RLS policies have a name and are applied to and removed from a table with ALTER statements. Policies are defined with a USING clause that returns a boolean value, which indicates whether to process a given row in the table.

The following should to be considered when using RLS:

* Applications should connect to the database as a user other than the owner or creator of the database objects.
* Postgres admin users and any role created with the BYPASSRLS attribute are not subject to RLS table policies.
* By default, the table owner bypasses RLS policies unless the table is altered with FORCE ROW LEVEL SECURITY.

When configured correctly, no rows will be returned or accessible in a table if the value specified in the `USING` clause for RLS has not been set prior to executing a query. 
