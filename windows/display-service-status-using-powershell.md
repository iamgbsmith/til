# Display Service Status Using PowerShell

__Category: Windows__

PowerShell can show the status of services, such as whether they are stopped or started.

For example, to list the status of services which match the wildcard `ssh` enter the following PowerShell command:

```command
Get-Service | ?{$_.Name -like '*ssh*'} | select -Property Name, StartType, Status
```

Output:

```command
Name      StartType  Status
----      ---------  ------
ssh-agent Automatic Running
```

__Note:__ Name will match on a process/executable name.
