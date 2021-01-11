# Working With Branches

__Category: Git__

A branch in Git is a lightweight movable pointer to a commit. The default branch name in Git is master.

### List all branches

```shell
git branch
```

### List all local and remote branches

```shell
git branch -av
```

### Create a new branch called feature/user-login-timeout

```shell
git branch feature/user-login-timeout
```

### Switch to a branch

```shell
git checkout feature/user-login-timeout
```

### Merge branch feature/user-login-timeout into master

```shell
git checkout master
git merge feature/user-login-timeout
```

### Delete a branch

```shell
git branch -d feature/user-login-timeout
```

### Tag the current commit

```shell
git tag my_tag
```
