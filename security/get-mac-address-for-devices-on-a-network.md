# Get MAC Address For Devices On A Network

__Category: Security__

Address Resolution Protocal (ARP) can be used to discover and display details about systems on your network including the MAC address of other devices. Entries are stored in the ARP cache which contains the mapping of IP Addresses to MAC Addresses for hosts on the local network.

Show entries in the ARP cache will full output:

```shell
arp -a
```

Show entries in compact mode:

```shell
arp -n
```

__Note:__ The `arp` utility is pre-installed on macOS although it may need to be installed on Linux depending on your distro.
