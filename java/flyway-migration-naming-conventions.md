# Flyway Migration Naming Conventions

__Category: Java__

Flyway is a database migration tool that allows for versioning of database schema and data changes for a broad ranging of database including Postgres, SQL Server, Oracle, Snowflake, DB2, and MySQL. Changes are written using plain SQL scripts and can be applied using auto-migration on startup of your application.

There are three types of migrations in Flyway:

* Versioned migrations - used to create tables or indexes and have a prefix of `V`
* Undo migrations - used to drop tables or indexes and have a prefix of `U`
* Repeatable migrations - used to insert reference or static data and have a prefix of `R`

Versioned migrations should start with a V, include a version number, two underscores, and a description of the change. For example:

```shell
V1__create_country_codes_table.sql
V2__create_vehicle_manufacturers_table.sql
```

Undo migrations should start with a U, include a version number, two underscores, and a description of the change. For example:

```shell
U1__drop_event_table.sql
```

Repeatable migrations should start with an R, include a version number, two underscores, and a description of the change.

```shell
R1__insert_country_codes_data.sql
R2__insert_vehicle_manufacturers_data.sql
```

Flyway can be configured to validate the name of files prior to migration using the following configuration setting:

```shell
flyway.validateMigrationNaming=true
```
