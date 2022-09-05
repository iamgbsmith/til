# Install OpenSSH On Windows

__Category: Windows__

By default, Windows ships with the OpenSSH client installed but not the server. 

To show with OpenSSH components are installed, run the following PowerShell command:

```command
Get-WindowsCapability -Online | ? Name -like 'OpenSSH*'
```

If the OpenSSH.Server shows as "NotPresent" you will need to install it as follows:

```command
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
```

Start the OpenSSH daemon:

```command
Start-Service sshd
```

Configure the OpenSSH daemon to start automatically:

```command
Set-Service -Name sshd -StartupType 'Automatic'
```
