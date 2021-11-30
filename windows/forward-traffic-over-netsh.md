# Forward Traffic Over Netsh

__Category: Windows__

You can forward traffic for a remote machine using network shell `netsh` to a port running locally. You might need to do this when connecting to an application running in WSL 2.

For example, to map port 8080 on `192.168.101.100` to port 8080 locally, enter the following command on your local machine with the PowerShell command:

```command
netsh interface portproxy add v4tov4 listenport=8080 listenaddress=0.0.0.0 connectport=8080 connectaddress=192.168.101.100
```

You may need to configure the Windows firewall to allow incoming and outgoing traffic on the port (in this example, 8080).
