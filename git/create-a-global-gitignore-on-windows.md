# Create A Global Gitignore On Windows

__Category: Git__

In certain situations, you may have OS specific files across many different projects that you do not want to add to version control. To do this, create a file called `.gitignore_global` on your machine.

Create the file in your home directory using PowerShell:

```shell
New-Item "%USERPROFILE%\.gitignore_global"
```

Add system entries to this file:

```text
# Windows
Thumbs.db
.idea
```

Configure git to use `.gitignore_global` with PowerShell.

```shell
git config --global core.excludesfile "$Env:USERPROFILE\.gitignore_global"
```
