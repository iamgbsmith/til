
# Create Release Notes Using Git

__Category: Git__

You can summarise commits on a branch using the `git shortlog` command which can be used to help prepare release notes.

Commits will be grouped by author and the first line of each commit message will be displayed.

Show all commits on a branch:

```shell
git shortlog
```

Show commits after a specific date:

```shell
git shortlog --after="1 Nov 2022"
```

Show commits using a date range, piping the output to a text file:

```shell
git shortlog --after="1 Oct 2022" --before "1 Nov 2022" > commit-history.txt
```
