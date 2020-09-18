# UUIDs As Primary Keys

Postgres supports Universally Unique Identifier (UUID) objects for primary keys using one of several standard algorithms. UUIDs are a good choice for primary keys for the following reasons: 

* They reduce the chance of an insecure direct object reference in APIs as the primary key for objects is harder to guess.
* They allow for easier data migrations between a source and target database due to a very low chance of duplicate keys or clashes.
* You can know the primary key before insertion which avoids a round trip to the database. This is useful in the situation where tables need to be populated with a foreign key based on the parent object.
* High-performance inserts are possible through the generation of UUIDs for row data prior to the insert. Records can be created in memory then flushed to the database in a single operation.

### Install the UUID module

`uuid-ossp` is a contrib module and is not installed into the server by default. You must either install it into each database that requires it or into a database template.

```sql
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
```

### Confirm the UUID extension is working

Generate a version 4 UUID, which is derived entirely from random numbers.

```sql
SELECT uuid_generate_v4();
```

### Create a table using a version 4 UUID as the primary key

```sql
CREATE TABLE IF NOT EXISTS books (
    id uuid NOT NULL default uuid_generate_v4() PRIMARY KEY, 
    title text NOT NULL,
    author_id uuid NOT NULL
    purchase_date timestamp(3) WITH TIME ZONE NOT NULL,
    description text
);
```

__Note:__ Compared to a typical 32-bit integer synthetic key, UUIDs incur a storage overhead because the inserted tuple is 128-bit. The row to write is 12 bytes bigger and you can fit fewer rows into a given amount of RAM. Additionally, the b-tree index that implements the primary key will be 4 times as large (vs a 32-bit key) taking longer to search and requiring more memory for caching.

See [PostgreSQL uuid-ossp](https://www.postgresql.org/docs/current/uuid-ossp.html) for more details.
