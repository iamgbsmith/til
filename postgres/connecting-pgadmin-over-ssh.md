# Connecting pgAdmin Over SSH

I struck a permissions problem connecting to a remote Postgres instance using pgAdmin. For security reasons, configuration in pg_hba.conf was restricting the IP address for incoming connections preventing me from directly accessing the server from my local machine because it wasn't whitelisted.

The solution was to create a tunnel over SSH specifying the local port to use when binding to the Postgres port at the remote address. Connections were established using an account on the database server.

Create an SSH tunnel as follows:

```
$ ssh -L 1111:localhost:5432 user@dbserver
user@dbservers's password: 
Welcome to Ubuntu 18.04.1 LTS
```

In the above example, traffic is being tunnelled to my local machine on port 1111 from the remote machine address port 5432. I used 1111 locally since I’m also running PG and port 5432 was unavailable.

After that, in pgAdmin I created a connection to the server on localhost:1111 using the appropriate credentials and I could run queries against the remote database server.
