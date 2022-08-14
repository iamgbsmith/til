# List Running Processes Using PowerShell

__Category: Windows__

You can list running processes in PowerShell using either the `Get-Process` or `ps` alias command.

To list all running processes:

```shell
Get-Process
```

To list running instances of Microsoft Teams:

```
Get-Process teams
```

To list running instances of Microsoft Teams and Word (process names are case insensitive):

```
Get-Process teams,winword
```

To show name, product version and the vendor for a running process follow it with the `Select-Object` pipe:

```
Get-Process teams | Select-Object name,productversion,company teams
```
