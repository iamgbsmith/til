# List Azure Regions And Locations Using The Azure CLI

__Category: Azure__

You can list full details for all Azure regions and locations in JSON format using the following command:

```shell
az account list-locations --out json
```

To list regional details and physical location in tabular format, use the following command:

```shell
az account list-locations --query "[].{regionalDisplayName:regionalDisplayName, physicalLocation:physicalLocation, name:name]" --out table
```


To list the regional display name, region name, and physical location (where applicable), sorting by name:

```shell
az account list-locations --query "sort_by([].{regionalDisplayName:regionalDisplayName, physicalLocation:metadata.physicalLocation,name:name},&name)" --out table
```
