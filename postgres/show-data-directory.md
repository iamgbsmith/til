# Show Data Directory

__Category: Postgres__

You can display the location for the Postgres data directory on Linux or macOS using the following command:

```shell
psql -U postgres -c 'SHOW data_directory'
```

Sample output:

```shell
                        data_directory                        
--------------------------------------------------------------
 /Users/joebloggs/Library/Application Support/Postgres/var-12
 ```
