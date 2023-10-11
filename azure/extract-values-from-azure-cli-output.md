# Extract Values From Azure CLI Output

__Category: Azure__

Output from Azure CLI commands can be extracted for use in scripts or IaC.

For example, assume `az account show --query` prints the following:

```json
{
  "environmentName": "Azurecloud",
  "homeTenantId": "01010101-1010-0101-1010-010101010101",
  "id": "60aae750-9d12-4739-a6a1-98ce329c7d4",
  "isDefault": "true",
  "managedByTenants": [],
  "name": "Azure Playground",
  "state": "Enabled",
  "tenantId": "01010101-1010-0101-1010-010101010101",
  "user": {
    "name": "bob.jackson@soundbytes.dev",
    "type": "user"
  }
}
```

To extract the value for subscription `id`, use the following command:

```shell
az account show --query id --output tsv
```

Output:

```shell
60aae750-9d12-4739-a6a1-98ce329c7d4
```

To get user name, use the following command:

```shell
az account show --query user.name --output tsv
```

Output:

```shell
bob.jackson@soundbytes.dev
```
