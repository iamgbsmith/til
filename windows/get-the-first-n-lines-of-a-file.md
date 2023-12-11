# Get The First N Lines Of A File

__Category: Windows__

You can get the first n lines of a text file using PowerShell with the "Get-Content" command.

To get the first 20 lines from a file called `log-entries.txt`, use the following command:

```shell
Get-Content -Path .\log-entries.txt -TotalCount 20
```

To get the content at a specific line, for example, line 20:

```shell
(Get-Content -Path .\log-entries.txt -TotalCount 20)[-1]
```
