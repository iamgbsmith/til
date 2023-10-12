# Create A Global Gitignore On MacOS

__Category: Git__

In certain situations, you may have OS specific files across many different projects that you do not want to add to version control. To do this, create a file called `.gitignore_global` on your machine.

Create the file in your home directory:

```shell
touch ~/.gitignore_global
```

Add system entries to this file:

```text
# Mac
.DS_Store
.AppleDouble
.idea
```

Configure git to use `.gitignore_global`:

```shell
git config --global core.excludesfile ~/.gitignore_global
```
