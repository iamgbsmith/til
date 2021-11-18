# Configure SSH Agent To Automatically Start

__Category: Windows__

By default, Windows does not automatically start the `ssh-agent`. 

To start the SSH agent automatically, enter the following command in PowerShell:

```command
Get-Service ssh-agent | Set-Service -StartupType Automatic -PassThru | Start-Service
```

Manually start the service:

```command
Start-Service sshd
```
