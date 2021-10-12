# Store Passwords Securely

__Category: Postgres__

For security reasons, passwords should always be stored in a database using a secure hashing algorithm. You should never store passwords in plaintext, and never use the SHA-1 hash function as it is considered weak.

Postgres supports storing of values securely using `pgcrypto`.

### Install the pgcrypto module

```sql
CREATE EXTENSION IF NOT EXISTS "pgcrypto";
```

### Insert value using the crypt function

Assuming a table called `users`, hash the password `p@55wordtoH@sh` using the Blowfish cipher function with a random salt as follows:

```sql
INSERT INTO users(id, email, enabled, first_name, id, last_name, password, username)
  VALUES ('49da16cd-c184-43b6-a362-8bdc8e723df2', 'joey@ramones.com', true, 'Joey', 'Ramone', 
  (select crypt(('p@55wordtoH@sh'), gen_salt('bf'))), 'joeyr')
```

The `gen_salt` function will force Postgres to generate a random salt for the hashed password.

If required, validate the entry has been stored with `crypt` as follows:

```sql
SELECT id 
FROM users
WHERE email = 'joey@ramones.com' 
AND password = crypt('p@55wordtoH@sh', password);
```

__Note:__ The Blowfish algorithm has a maximum password length of 72 characters. Alternative hashing functions include `md5` which has a theoretically unlimited length password length.