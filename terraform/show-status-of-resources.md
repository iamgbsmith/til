# Show Status Of Resources

__Category: Terraform__

Resources in Terraform can be inspected using the `terraform show` or `terraform state` commands. 

`state` commands expect a sub-command to be passed in as an argument.

To display the current state of all resources:

```command
terraform show
```

To display a compact list of resources:

```command
terraform state list
```

To display state for a specific resource, for example, one called `docker_container.nginx` use the following command:

```command
terraform state show docker_container.nginx
```
