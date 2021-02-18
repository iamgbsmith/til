# Search An LDAP Server

__Category: Security__

You can search an LDAP server from the command line on Linux or macOS using `ldapsearch`.
 
For example, to list all matching entries in the “people” Organisational Unit (OU) against an LDAP server:
 
 ```shell
ldapsearch -h ldap.orbiks.org:636 -D uid=billyt,ou=people,dc=orbiks,dc=org -W -b ou=people,dc=orbiks,dc=org objectclass=*
```

Or, specify the scheme (ldap/ldaps) and host using `-H`:

 ```shell
ldapsearch -H ldaps://ldap.orbiks.org -D uid=billyt,ou=people,dc=orbiks,dc=org -W -b ou=people,dc=orbiks,dc=org objectclass=*
```

In the above examples:

* `636` is the port for the LDAP server (the default port for LDAP is 389; the default port for LDAPS is 636)
* `-D` is used to specify the distinguished name (DN) the bind account which is performing the search
* `-W` will prompt for the password
* `-b` is the base DN for search
* `objectclass=*` is the type of object to search for (in this case, wildcard will search for all objects)

__Note:__ 
* Do not use the lowercase `-w` option to specify the password as it will be visible in the command history.
* LDAP DNs and all attributes are case-insensitive by default.

See [How to write LDAP search filters](https://confluence.atlassian.com/kb/how-to-write-ldap-search-filters-792496933.html) for details on constructing objectclass filters.
