# Undoing Changes

__Category: Git__

The `git reset` and `git revert` can be used to undo changes in a repository. The former command allows you to manipulate either commits or individual files.

It is important to consider that before changes are committed to the repository history, they live in the staging index and the working directory. 
## Which command should you use?

The command to use depends on whether the changes are committed or uncommitted.

### Undo all changes in a private branch

To remove all changes on a private branch that are uncommitted, use the `git reset` command. If you want to retain any files that were created on the branch use the `--soft` option (__do not use the `--hard` option unless you want to delete all changes in the working directory__):

```shell
git reset --soft
```

### Undo changes to a specific file in a private branch

To abandon changes on a file in a private branch, specify the file/path. 

To reset a specific file called `index.html` to the most recent previous version:

```shell
git reset index.html
```

The following command will fetch the version of `index.html` in the third-to-last commit and stage it for the next commit:

```shell
git reset HEAD~3 index.html
```

### Undo changes in a public commit

Reverting undoes a commit by creating a new commit. It is a safe way to undo changes because it does not re-write the commit history.

For example, the following command will determine changes contained in the second to last commit, create a new commit undoing those changes, and add the new commit onto the existing project for the current branch.

```shell
git revert HEAD~2
```
