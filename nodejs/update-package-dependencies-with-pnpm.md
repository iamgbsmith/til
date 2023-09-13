# Update Package Dependencies With PNPM

__Category: Nodejs__

Use the `pnpm outdated` command to list which dependencies in `package.json` need updating. 

Update all package dependencies without prompting:

```shell 
pnpm up
```

Interactively update all package dependencies:

```shell 
pnpm up -i
```

Interactively update prod package dependencies:

```shell
pnpm up -P -i
```

Interactively update dev package dependencies:

```shell
pnpm up -D -i
```
