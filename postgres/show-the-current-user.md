# Show The Current User

__Category: Postgres__

You can show the name of the user who has established a connection to Postgres using the following command:

```sql
SELECT current_user;
```

Output:

```
current_user    
--------------------
 coolapp_dbusr
(1 row)
```
