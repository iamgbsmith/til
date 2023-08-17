# Pass Variables To Terraform

__Category: Terraform__

Variables can be passed to Terraform from the command line using the `-var` parameter.

Assume a `variables.tf` file:

```javascript
variable "environment_name" {
  type = string
  description = "The name of the environment."
}


variable "location" {
  type = string
  description = "The Azure region where the resources will be created. The default is westeurope."
  default = "westeurope"
}
```

Assume you want to specify a value for `environment_name` which does not have a default:

```shell
terraform plan -var environment_name="dev"
```
