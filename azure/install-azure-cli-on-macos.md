# Install Azure CLI On MacOS

__Category: Azure__

The Azure CLI is used to interact with Azure services from the command line.

### Install on macOS

Installation can be done using brew.

```shell
brew update && brew install azure-cli
```

Show the installed version:

```shell
az --version
```

### Update on macOS

Updates to the CLI are released on a regular basis. You can upgrade to the latest version as follows:

```shell
az upgrade
```

### Uninstall on macOS

If you need to uninstall, use the following command:

```shell
brew uninstall azure-cli
```

If you do not plan to reuse the CLI in future, remove the data directory from your profile as follows:

```
rn -rf ~/.azure
```
