# List Azure Resource Groups

__Category: Azure__

You can list Resource Groups in an Azure subscription showing full details with the following command:

```shell
az group list
```

To show tab separated output:

```shell
az group list -o tsv
```

To show table output with name, location, and status:

```shell
az group list -o table
```

List groups in a location:

```shell
az group list --query "[?location=='eastus']"
```

To show only the name of the group in the output:

```shell
az group list --query "[].name" -o table
```

To get details for a specific group by name:

```shell
az group show --name foo-bar-baz
```
