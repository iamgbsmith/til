# Switch To A Specific Azure Subscription

__Category: Azure__

You can switch to a specific Azure subscription using the `account set` command.

List subscriptions:

```shell
az account list
```

Set the subscription using an id:

```shell
az account set --subscription=aa41bc21-beef-4631-8eea-d3cde1e40777
```

Show the subscription details:

```shell
az account show
```
