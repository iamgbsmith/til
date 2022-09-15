# Install Terraform On macOS

__Category: Terraform__

The steps outlined here will install Terraform on macOS using Homebrew.

### Install Terraform

Install the Hashicorp tap:

```shell
brew tap hashicorp/tap
```

Install Terraform:

```shell
brew install hashicorp/tap/terraform
```

Update Homebrew before updating Terraform:

```shell
brew update
```

Ensufre Terraform is running the latest version:

```shell
brew upgrade hashicorp/tap/terraform
```

### Verify installation

Open a new terminal and run the `-help` subcommand:

```shell
terraform -help plan
```
