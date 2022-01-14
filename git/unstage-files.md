# Unstage Files

__Category: Git__
  
You can unstage files that are ready for commit by using the `git restore` command.

For example, to unstage a file called `index.html`, use the following command:

```shell
git restore --staged /path/to/file/index.html
```

To unstage all changes:

```shell
git restore --staged .
```

Unstaged changes will remain on disk.
