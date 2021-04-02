# Install Command Line Tools

__Category: Mac__

Command Line Tools gives macOS users access to tools, utilities, and compilers, including make, GCC, clang, perl, svn, git, size, strip, strings, libtool, cpp, and other commands that are usually found in Linux installations.

If your code Command Line Tools are out of date you will see an error similar to the following:

```shell
Error: Your CLT does not support macOS 11.
It is either outdated or was modified.
Please update your CLT or delete it if no updates are available.
```

Delete the old version:

```shell
sudo rm -rf /Library/Developer/CommandLineTools
```

Install the latest version:

```shell
sudo xcode-select --install
```
