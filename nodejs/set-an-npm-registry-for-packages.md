# Set An NPM Registry For Packages

__Category: Nodejs__

You can configure `npm` or `yarn` to resolve package dependencies from a specific registry, for example, one running locally within a corporate network. This approach can be used for React, Angular, or other projects which use npm or yarn.

Scenarios where you may benefit from a registry other than the default at https://registry.npmjs.org/:

* You have limited internet connectivity
* Build time performance will be reduced
* Security policies necessitate it
* Caching locally will reduce internet traffic

### Show the current registry

```shell
npm config get registry
```

Output:

```shell
https://registry.npmjs.org/
```

### Set registry globally at the command line

To set a registry globally from the command line, enter the following command:

```shell
npm config set registry https://orbiks.com/some-npm-registry/
```

### Set registry for a specific project

Create a file called `.npmrc` in your project root directory and add the following:

```shell
https://orbiks.com/some-npm-registry/
```

### Optionally, log into your registry

You may need to perform a one-off authentication with your registry.

Login to npm, entering your account credentials when prompted:

```shell
npm login
```
