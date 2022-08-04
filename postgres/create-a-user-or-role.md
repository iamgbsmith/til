# Create A User Or Role

__Category: Postgres__

For this TIL, a user called `orbiks_dbsvc` will be created using PSQL.

__Do not create a user from the command line using plaintext passwords.__

### Create the user

```sql
CREATE USER orbiks_dbsvc PASSWORD 'b@dpa55w0rd';
```

The above command is identical to:

```sql
CREATE ROLE orbiks_dbsvc WITH LOGIN PASSWORD 'b@dpa55w0rd';
```

Create a user with an account valid until a specified date and a limit of 50 database connections:

```sql
CREATE USER orbiks_dbsvc
ENCRYPTED PASSWORD 'b@dpa55w0rd' 
VALID UNTIL '2023-12-31'
CONNECTION LIMIT 50;
```

Delete a user:

```sql
DROP USER orbiks_dbsvc;
```

### Password hashing methods

Password should be hashed using the SCRAM-SHA-256 algorithm. This is a challenge-response scheme that prevents password sniffing on untrusted connections and supports storing passwords on the server in a cryptographically hashed form that is considered to be secure.

Ensure that `postgresql.conf` uses the following setting:

```shell
password_encryption = scram-sha-256
```

Following user creation, `GRANT` access permissions using the principle of least privilege.
