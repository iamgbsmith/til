# List Role Assignments Using The Azure CLI

__Category: Azure__

### Show user role assignment

Role assigments can be for an Azure AD user, group, service principal, or subscription.

You can list role assignments for a user based on their user principal name (email address) or their user object Id.

Get the user object id:

```shell
az ad user show --id "{principalName}" --query "id" - -output tsv
```

Example call:

```shell
az ad user show --id "bob.jackson@microspan.com" --query "id" --output tsv
```

List role assignments using the object id for the user in tabular format:

```shell
az role assignment list --all --assignee "6c967980-1406-4328-94ad-b315364b8224" --query "[].{principalName:principalName,roleDefinitionName:roleDefinitionName, scope:scope}" --output tsv
```

List role assignments using the principal name for the user in JSON format:

```shell
az role assignment list --all --assignee bob.jackson@microspan.com --query "[].{principalName:principalName,roleDefinitionName:roleDefinitionName,scope:scope}"
```

### Show group role assignment

Get the group object id:

```shell
az ad group show --group "{groupName}" --query "id" --output tsv
```

You can show who has been assigned a role for a resource group. 

The following command will list role assignments showing role definition and principal names in tabular format:

```shell
az role assignment list --resource-group "{groupId}" --query "[].{roleDefinitionName:roleDefinitionName,principalName:principalName}" --output tsv
```

### Variations

To list role assignments for a subscription use:

```shell
az role assignment list --subscription {subscriptionNameOrId} --output json --query "[].{principalName:principalName,roleDefinitionName:roleDefinitionName,scope:scope}"
```

To list role assignents for a service principal in tabular format:

```shell
az ad sp list --display-name "{name}" --query "[].id" --output tsv
```

__Note:__ You do not need to surround user principal names or object id values using double quotes. When searching based on a name which contains spaces, use double quotes.
