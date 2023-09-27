# Create A Resource Group Using The Azure CLI

__Category: Azure__

Resource groups can be created using the Azure CLI. You must specifiy a location and name when creating.

You can check whether the resource group exists with the following command:

```shell
az group exists --name rg-some-resource-group
```

Create a resource group called `rg-orbiks-dev-eastus` in the current account subscription:

```shell
az group create --location eastus --name rg-orbiks-dev-eastus -001
```

Create a resource group in `uksouth` called `rg-proto-dev-uksouth-002` for a specific subscription and apply tags:

```shell
az group create --location westus --name rg-proto-dev-uksouth-002 --subscription d3fba33f-28db-4743-bdf6-4f86492909e2 --tags owner-bobjackson@soundbytes.dev project=infospan environment=dev
```
