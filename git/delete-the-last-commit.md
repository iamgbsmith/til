# Delete The Last Commit

__Category: Git__

In some situations you might need to delete the last commit from a repository changelog. For example, where you accidentally commit information that contains sensitive data or commit a large binary file. 

__Before running this command, ensure you have backed up any changes in your working directory that you wish to keep.__ 

### Preserve changed files and delete the last commit

If you want to delete the last commit on the current branch and retain changed files, you can use the `--soft` flag:

```shell
git reset --soft HEAD~1
```
### Abandon changed files and delete the last commit

If you want to delete the last commit on the current branch and lose changed files, you can use the `--hard` flag:

```shell
git reset --hard HEAD~1
```
### Push changes to remote branch

After performing a git reset, force push to the remote branch:

```shell
git push --force
```

__Note: Git reset is a solution that should only be used as a last resort. Be careful performing a reset as it could affect other users working on the same repository.__
