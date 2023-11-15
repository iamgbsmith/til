# List Service Principals Using The Azure CLI

To list service principals for a subscription, use the following command:

```shell
az ad sp list
```

List service principals for a subscription showing specific fields in JSON format:

```shell
az ad sp list --query "[].{accountEnabled:accountEnabled, appDisplayName:appDisplayName, appId:appId, id:id, createdDateTime:createdDateTime}"
```

List service principals for a subscription showing specific fields in tabular format:

```shell
az ad sp list --query "[].{accountEnabled:accountEnabled, appDisplayName:appDisplayName, appId:appId, id:id, createdDateTime:createdDateTime}" --output tsv
```

If you need to output to a file for further inspection, pipe to a tab separated file using `> service-principal-search.tsv` on Windows or `| service-principal-search.tsv` on macOS then import the file into Excel.