# Show Config File Location

__Category: Postgres__

You can display the location for the Postgres configuration on Linux or macOS using the following command:

```shell
psql -U postgres -c 'SHOW config_file'
```

Sample output:

```shell
                                 config_file                                  
------------------------------------------------------------------------------
 /Users/joebloggs/Library/Application Support/Postgres/var-12/postgresql.conf
 ```
