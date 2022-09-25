# SSH Into WSL From Another Machine

__Category: Windows__

You can SSH into WSL from another machine by port forwarding SSH traffic to the Windows host using `netsh` and punching a hole in the Windows firewall. This example will map port 22 on the WSL instance to port 7222 on the Windows host and enable password authentication.

__Note:__ Password authentication is an alternative to SSH public key authentication.

### Configure SSH on the WSL instance

Configure SSH on WSL to prompt for a password by editing `/etc/ssh/sshd_config` ensuring the following value is set to disallow sending clear text passwords:

```shell
PasswordAuthentication no
```

Enable challenge-response password authentication for SSH:

```shell
ChallengeResponseAuthentication yes
```

### Start SSH on the WSL instance

Check the status of SSH on the WSL instance:

```shell
sudo service ssh status
```

If required, restart the SSH daemon to ensure any changes are committed:

```shell
sudo service ssh restart
```

### Forward the SSH port

To map port 22 on the WSL IP Address running at `172.18.80.220` to port 7222 on Windows, run the following PowerShell command on your Windows machine:

```command
netsh interface portproxy add v4tov4 listenport=7222 listenaddress=0.0.0.0 connectport=22 connectaddress=172.18.80.220
```

__Note:__ The assigned IP address proxied using `netsh` for a WSL instance needs to be set when the WSL instance restarts. 

### Allow SSH traffic through the Windows firewall

Allow SSH traffic over port 7222 using `netsh`:

```command
netsh advfirewall firewall add rule name=”Open the SSH Port for WSL” dir=in action=allow protocol=TCP localport=7222
```

Connect to the WSL instance using SSH on port 7222. In the following command, the username for the WSL Linux account is `joesoap` and the IP address specified is for the Windows machine:

```shell
ssh joesoap@192.168.68.105 -p7222
```

You will be prompted to enter your password.
