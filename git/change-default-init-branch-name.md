# Change Default Init Branch Name

__Category: Git__

Git uses `master` as the default branch name when initialising a project.

Starting in Git 2.28, `git init` will instead look to the value of `init.defaultBranch` when creating the first branch in a new repository. If that value is unset, `init.defaultBranch` defaults to master.

To change the default branch to something else (for example `main`) use the following command:

```shell
git config --global init.defaultBranch main
```

After setting this variable, running `git init` will produce a repository whose initial branch is main.

```shell
git init
Initialised empty Git repository in /path/to/my-application/.git/

git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

See [Git - Introducing init.defaultBranch](https://github.blog/2020-07-27-highlights-from-git-2-28/#introducing-init-defaultbranch) for more details.