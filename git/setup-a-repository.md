# Setup A Repository

__Category: Git__

The steps outlined here assume you have created a project locally and want to synchronise to a remote Git repository. For this example, the remote repository is hosted on GitHub.

__Note:__ 
* GitHub changed from using `master` to `main` as the default branch for repositories in June 2020.
* It is a pre-requisite to have configured an SSH key for interacting remotely with the Git repository.

Change to the root directory for your project:

```shell
cd /path/to/app
```

### Create a new repository on the command line

Initialise a Git repository and add files in the working directory:

```shell
git init
git add .
git commit -am "Initial commit"
git branch -M main
git remote add origin git@github.com:{username}{repository-name}.git
git push -u origin main
```

### Push an existing repository from the command line

This assumes that there is nothing contained in the remote repository.

From an existing Git repository: 

```shell
git remote add origin git@github.com:{username}/{repository-name}.git
git branch -M main
git push -u origin main
```

You should ensure that your repository includes `README.md`, `LICENSE.md` and `.gitignore` files.
