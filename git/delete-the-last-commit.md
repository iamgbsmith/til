# Delete The Last Commit

__Category: Git__

In some situations you might need to delete the last commit from a repository changelog. For example, where you accidentally commit information that contains sensitive data or commit a large binary file. 

__Before running this command, ensure you have backed up any changes in your working directory that you wish to keep.__ 

### Reset by deleting the last commit

Assuming you want to delete the last commit on the current branch, you can use `HEAD~1`:

```shell
git reset --hard HEAD~1
```

Force push to the remote branch:

```shell
git push --force
```

__Note: Git reset is a solution that should only be used as a last resort. Be careful performing a reset as it could affect other users working on the same repository.__
