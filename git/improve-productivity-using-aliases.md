# Improve Productivity Using Aliases

__Category: Git__

Aliases can be used to make you more productive with Git. For example, instead of typing `git commit`, you just type `git ci`.

List aliases:

```shell
git alias
```

or

```shell
git config --get-regexp alias
```

Create aliases:

```shell
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

See [Git Aliases](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases) for more details.