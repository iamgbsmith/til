# Follow Symbolic Links

__Category: Mac__

Files can use symbolic links (symlinks) which resolve to a different location on the filesystem. You can follow symbolic links by including `-L` in the command.

For example, to list files by date order which resolve using symbolic links:

```shell
ls -ltr -L /Users/gregsmith/Library/Containers/foo.bar.baz/Data/Pictures
```
