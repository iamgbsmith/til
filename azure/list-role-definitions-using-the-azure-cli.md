# List Role Definitions Using The Azure CLI

__Category: Azure__

To list full details for role defintions (roles that can be assigned), use the following command:

```shell
az role definition list
```

List role definitions for specific fields in JSON format:

```shell
az role definition list --query "[].{id:id, name:name, roleType:roleType, roleName:roleName]"
```

List role definitions for specific fields in tabular format:

```shell
az role definition list --query "[].{name:name, description:description, roleName:roleName]" --output tsv
```

__Note:__ In the above examples, `name` is the UUID of the role.
