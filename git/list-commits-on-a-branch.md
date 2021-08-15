# List Commits On A Branch

__Category: Git__

You can list commits for a specific branch with the following command:

```shell
git log main
```

Use the `oneline` flag to display the commits for a specific branch in a verbose format:

```shell
git log main --oneline
```

The output of the log is a separate line showing the hash and the message for each specific commit.

Alternatively, list all commits for a branch since it was branched:

```shell
git log main..feature-branch-name --oneline
```
