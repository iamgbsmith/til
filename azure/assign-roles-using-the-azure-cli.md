# Assign Roles Using The Azure CLI

__Category: Azure__

### List available roles

Access to Azure resources is granted by assigning roles to users, groups, service principals, or managed identities using Azure role-based access control (Azure RBAC).

You can list roles assigned to a user based on their user id:

```shell
az role assignment list --assignee {userId}
```

Role assignment requires `Microsoft.Authorization/roleAssignments/write` permissions for Owner or User Access Administrator.

Use the following command to list roles that can be assigned:

```shell
az role definition list --query "[]{name:name, roleType:roleType, roleName:roleName}" --output tsv
```

To show details for a specific role:

```shell
az role definition list --name "{roleName}"
```

### Assign roles

You should assign roles using the principle of least privilege. Azure provides four levels of scope when assigning a role:

* Resource
* Resource Group
* Subscription
* Management Group

__Note: You must specify a scope wheb assigning a role.__

To assign a role for a user in a specific resource group:

```shell
az role assignment create --assignee "{assignee}" role "{roleNameorId}" --resource-group "{resourceGroupName}" --scope "/subscriptions/{subscriptionId}/resourceGroups/name-of-resource-group™
```

To assign a role based on a role id using the service principal name (change the subscription id to match yours):

```shell
az role assignment create --assignee "walter.fagan@microspan.com" --role "f10789d7-075-45cd-b8cf-85475e164cfa" --resource-group "name-of-resource-group" --scope "/subscriptions/{subscriptionId}/resourceGroups/name-of-resource-group"
```

To assign a role based on a role name using the service principal id (change the subscription id to match yours):

```shell
az role assignment create --assignee "e0c00726-468f-4ca2-aa56-ea2908c3b893" --role "FHIR SMART User" --resource-group "name-of-resource-group" --scope "/subscriptions/{subscriptionId}/resourceGroups/name-of-resource-group"
```
