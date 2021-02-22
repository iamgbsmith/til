# Display Environment Variables

__Category: Linux__

You can display environment variables using the `printenv` command.

On a system with a large number of environment variables you may need to pipe the output to less as follows:

```shell
printenv | less
```

To search for a specific environment variable use `grep` followed by the search string (searches are case sensitive)

```shell
printenv | grep HIST
```

The `printenv` command also works the same on macOS.
