# Configure Git Settings

__Category: Git__

Git configuration only needs to be done once if you pass the `--global` option because it will always use that information for anything you do on that system. 

### Configuration Settings

Check your configuration settings using:

```shell
git config --list
```

Set your identity that will be associated with each history marker:

```shell
git config --global user.name "Billy Bragg"
git config --global user.email billybragg@orbiks.com
```

Set automatic command line colours to allow for easy reviewing.

```shell
git config --global color.ui auto
```

Git uses the default system editor. If you want to use a different text editor such as Emacs, specify the following:

```shell
git config --global core.editor emacs
```

__Note:__ If you want to override global configuration for a project, for example, to specify a different name or email address then run the command with the `--local` option for the project directory you are working in.

See [First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) for more details.