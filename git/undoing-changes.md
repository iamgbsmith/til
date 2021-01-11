# Undoing Changes

__Category: Git__

Before changes are committed to the repository history, they live in the staging index and the working directory. 

If you have made changes locally and need to remove these from your local working copy, issue the following command: 

```shell
git reset
```

This will have the effect of removing changes which were comitted to the local repository but not pushed to the remote repository. 

Any files that were created on the branch will remain on the file system.