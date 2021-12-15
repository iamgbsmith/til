# Upgrade PowerShell

__Category: Windows__

PowerShell will indicate whether an upgrade is required when you see the following message:

```command
 A new PowerShell stable release is available: v7.2.1
 Upgrade now, or check out the release page at:
    https://aka.ms/PowerShell-Release?tag=v7.2.1
```

Use the following to launch the PowerShell upgrade from the command line, following the steps in the MSI installer:

```console
iex "& { $(irm https://aka.ms/install-powershell.ps1) } -UseMSI"
```

Relaunch PowerShell. Display the version with the following command:

```command
(Get-Command 'C:\Program Files\PowerShell\7\pwsh.exe').Version
```
