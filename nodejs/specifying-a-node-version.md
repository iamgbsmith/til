# Specifying A Node Version

__Category: Nodejs__

Assuming you have installed `nvm`, create a file called `.nvmrc` in the root of your project and specify the version of Node to use.

```text
lts/fermium
```

Switch to the Node version required by the project with the following command:

```shell
nvm use
```

Output: 

```shell
Found '/path/to/project/.nvmrc' with version <lts/fermium>
Now using node v14.15.5 (npm v6.14.11)
```

Ensure you commit the `.nvmrc` file to version control.
