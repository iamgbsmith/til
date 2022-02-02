# Detect Open Ports Using Nmap

__Category: Security__

__Disclaimer: Do not use Nmap on a network or against a host unless you have explicit permission to do so__

Nmap allows network admininstrators and penetration testers to find devices running on their network, discover open ports and services, or detect vulnerabilities.

Scan a single port on a target host:

```shell
nmap 192.168.1.10 -p 8080
```

Scan a range of ports on a target host, separating the range using a hyphen:

```shell
nmap 192.168.1.10 -p 6000-8080
```

Scan the top n ports on a list of target hosts using the `-top-ports` flag. Will check ftp, ssh, telnet, smtp, https, and other well-known ports.

```shell
nmap 192.168.1.10 192.168.1.44 --top-ports 20
```

Output for all of the above will show the port number, state (either open or closed) and the service type, e.g. ftp, ssh, telnet, etc.
