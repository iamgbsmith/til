# Perform A DNS Lookup

Linux/Unix/macOS provide the ability to lookup server details from the command line using the `host` command.

### Find the IP address associated with a domain name

For a given domain name, lookup the DNS to resolve to an IP address.

```
host www.google.com
```

Prints the following:

```
www.google.com has address 172.217.25.164
www.google.com has IPv6 address 2404:6800:4006:804::2004
```

Adding `-v` to the command will print out verbose information.

__Note:__ Not all servers on the internet can be resolved into IP addresses by these commands.

### Find the domain name associated with an IP address

For a given IP address, perform a reverse lookup to determine the domain name for an IP address if the host can be resolved. 

```shell
host 172.217.25.164
```

Prints the following:

```
164.25.217.172.in-addr.arpa domain name pointer syd09s13-in-f4.1e100.net.
164.25.217.172.in-addr.arpa domain name pointer sin01s16-in-f4.1e100.net.
164.25.217.172.in-addr.arpa domain name pointer syd09s13-in-f164.1e100.net.
```

__Note:__ In some cases, the IP address lookup might resolve to a Content Delivery Network (CDN) or edge server.

### Alternative commands

Alternatives to using `host` for resolving a domain name include `nslookup` and `dig`.