# Scan Networks Using Nmap

__Category: Security__

__Disclaimer: Do not use Nmap on a network or against a host unless you have explicit permission to do so__

Nmap allows network admininstrators and penetration testers to find devices running on their network, discover open ports and services, or detect vulnerabilities.

Scan a single host for well-known ports (can use an FQDN or IP address):

```shell
nmap 192.168.1.10
```

Perform a verbose scan against specific multiple hosts:

```shell
nmap 192.168.1.10 192.168.1.44 -vv
```

Scan devices on a subnet:

```shell
nmap 192.168.1.1/24
```

Perform a stealth scan against a host (this will be slower because the scan does not complete a 3-way handshake):

```shell
nmap 192.168.1.1 -sS
```

Fingerprint hosts (using a hyphen to specify a range), showing OS version and a list of services and versions where detectable: 

```shell
nmap 192.168.1.1-60 -sV
```

Perform an aggressive scan, showing OS version, a list of services and versions where detectable, and traceroute information:

```shell
nmap 192.168.1.1 -A
```
