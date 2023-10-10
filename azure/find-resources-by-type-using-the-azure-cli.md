# Find Resources By Type Using The Azure CLI

__Category: Azure__

You can find resources by a specific type for your subscription using the Azure CLI. Resource Type will be the value for the Resource Provider Namespace.

To find OpenAI Cognitive Services resources in your subscription, use the following command:

```shell
az resource list --resource-type Microsoft.CognitiveServices/accounts --query "[?kind=='OpenAI'].(name:name, location:location, resourceGroup:resourceGroup, kind:kind, createdBy: createdBy, createdAtcreatedAt, id:id)" --output tsv
```

To find Azure Static Web Apps in your subscription, use the following command:

```shell
az resource list --resource-type Microsoft.Web/staticSites --query "[].{name:name, location:location, resourceGroup:resourceGroup, kind:kind, createdBy:createdBy, createdAt:createdAt, id:id}" --output tsv
```

To list Function apps, use the following command:

```shell
az resource list --resource-type Microsoft.Web/sites --query "[].{name:name, location:location, resourceGroup:resourceGroup, kind:kind, createdBy:createdBy, createdAt: createdat, id:id)" --output tsv
```

If you need to output to a file for further analysis, pipe to a tab separated file using `> resource-search.tsv` on Windows or `| resource-search.tsv` on macOS then import the file into Excel.

See [Abbreviation examples for Azure resources](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations) for a list of Resource Provider Namespaces.