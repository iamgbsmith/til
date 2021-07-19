# Upgrading Package Dependencies

__Category: Nodejs__

After using the `yarn outdated` command, package dependencies can be upgraded selectively or using a wildcard expression.

To upgrade a package to a specific version:

```shell
yarn upgrade react --latest
```

To upgrade a package to the latest version:

```shell
yarn upgrade prismjs --latest
```

To upgrade all packages matching a specific name:

```shell
yarn upgrade --pattern gatsby --latest
```

See https://classic.yarnpkg.com/en/docs/cli/upgrade/
