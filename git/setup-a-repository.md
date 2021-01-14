# Setup A Repository

__Category: Git__

The steps outlined here assume you have created a project locally using an IDE or build tools and want to synchronise to a remote repository and that the default branch name is `main`.

__Note:__ 
* GitHub changed from using `master` to `main` as the default branch for repositories in June 2020.
* It is a pre-requisite to have configured an SSH key for interacting remotely with the Git repository.

Change to the root directory for your project:

```shell
cd /path/to/my-application
```

Initialise a Git repository (repo) and add the files:

```shell
git init
git add .
```

Associate with the remote repo:

```shell
git config pull.rebase false
git remote add origin git@github.com:youraccount/my-application.git
git pull git@github.com:youraccount/my-application.git main
```

Push to the remote repo:

```shell
git commit -S -am "Initial commit"
git push -u origin main
```
