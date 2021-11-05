# Forward Traffic Over An SSH Tunnel

__Category: Linux__

It may be necessary to forward traffic over an SSH tunnel if a remote machine is not allowing direct inbound comnections due to IP whitelisting. SSH encrypts all data in-flight.

For example, to map port 8275 on `remote.machine.orbiks.com` to port 8080 locally, enter the following command on your local machine:

```shell
ssh -L 8080:localhost:8275 username@remote.machine.orbiks.com
```

You may be prompted to enter your credentials as part of establising the SSH session.
