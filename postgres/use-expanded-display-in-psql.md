# Use Expanded Display In PSQL

__Category: Postgres__

Query output from `psql` can be difficult to read or span multiple lines if there are lots of columns for a given table.

Use expanded display to improve readability in psql with the following command:

```shell
vehicle_database=# \x
Expanded display is on.
```

Output from SQL commands will be displayed in extended table format.

```sql
vehicle_database=# select * from cars;
-[ RECORD 1 ]-----+--------------------------------------------------------
id                | ca643740-a1c6-4d4a-8dfa-f2de01b4b0d1
registered_date   | 2021-10-25 10:15:14+13
type              | SUV
manufacturer_name | Hyundai
model_id          | Kona
available         | t
-[ RECORD 2 ]-----+--------------------------------------------------------
id                | ab4cccfe-a567-4949-8273-b05f6fc5f073
registered_date   | 2021-09-17 10:17:00+13
type              | SUV
manufacturer_name | Porsche
model_id          | Macan GTS
available         | f
```

Issue the `\x` command again to turn expanded display off.
