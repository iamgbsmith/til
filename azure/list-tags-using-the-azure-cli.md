# List Tags Using The Azure CLI

__Category: Azure__

You can list tags assigned to resources using the Azure CLI.

To list tags for a resource group:

```shell
az tag list --resource-id /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}
```

If required, to list tags for a resource, first get the resource id for resources in a resource group, showing output in tabular format:

```shell
az resource list --resource-group {resourceGroupName} --query "[].{name:name, id:id)" --output tsv
```

List tags for a resource using the resource details (this will follow the pattern of /providers/Microsoft.xyz/foo/bar/baz):

```shell
az tag list --resource-id /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/{resourceDetails}
```
