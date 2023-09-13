# Update Package Dependencies With Yarn

__Category: Nodejs__

After using the `yarn outdated` command, package dependencies can be updated selectively or using a wildcard expression.

To update a package to a specific version:

```shell
yarn upgrade react --latest
```

To update a package to the latest version:

```shell
yarn upgrade prismjs --latest
```

To update all packages matching a specific name:

```shell
yarn upgrade --pattern gatsby --latest
```

To update packages interactively to the latest version:

```shell
yarn upgrade-interactive --latest
```

See https://classic.yarnpkg.com/en/docs/cli/upgrade/
