# Protect Azure Resources Using Locks

__Category: Azure__

You can protect Azure resources that you have created using locks.

Locks can exist at three different scopes: 

* Subscription
* Resource Group
* Resource 

Lock types are:

* `CanNotDelete` - the resource can be read and modified by authorised users but it cannot be deleted.
* `ReadOnly` - the resource can be read but it cannot be deleted or updated.
 
To create a subscription level lock, use the following command:

```shell
az lock create --name subscriptionName --lock-type ReadOnly
```

To list locks for a resource group, use the following command:

```shell
az lock list --resource-group resourceGroupName
```

If there are no locks on a resource group, the command will return an empty array.

To prevent a resource group from being deleted, apply `CanNotDelete` using the following command:

```shell
az lock create --name lockName --lock-type CanNotDelete --resource-group resourceGroupName
```

To delete a lock, use the following command:

```shell
az lock delete --name lockName --resource-group resourceGroupName
```

__Note:__ When you create a lock at a parent scope, all resources within that scope inherit the same lock including resources that are added later. The most restrictive lock in the inheritance hierarchy takes precedence.

See [Considerations before applying your locks](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources?tabs=json#considerations-before-applying-your-locks) for more details on lock restrictions.
