# Delete Resources Using The Azure CLI

__Category: Azure__

Deleting a resource within a resource group requires specifying the name and type of the resource. 

For example, use the following command to delete a Cognitive Services resource:

```shell
az resource delete --resource-group resourceGroupName --name resourceName --resource-type "Microsot.CognitiveServices/accounts"
```

You can delete a resource group and all resources contained within it using the following command:

```shell
az group delete --name resourceGroupName
```

__Note:__ You may not be able to delete resources if you do not have the correct permissions (for example, "Contributor" access).