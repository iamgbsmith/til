# Show Command History In PowerShell

__Category: Windows__

Command history in PowerShell can be displayed with the following command:

```command
 Get-History
```

Sample output:

```command
  Id     Duration CommandLine
  --     -------- -----------
   1        0.028 cd \
   2        0.019 cd .\Data\til\
   3        0.139 git status
   4        0.277 git diff .\README.md
   5        0.121 git add .\windows\install-wsl.md
   6        0.454 git commit -am "Windows - Install WSL"
   7        3.691 git push
  ```

To execute a previous command, invoke it based on the Id:

```command
Invoke-History 3
```

To show details on when a command was executed, use the following:

```shell
Get-History | Format-List -Property *
```

To search command history, enter the string literal after the `Pattern` flag. For example, to search for "commit", enter the following:

```command
Get-History |  Select-String -Pattern "commit"
```
