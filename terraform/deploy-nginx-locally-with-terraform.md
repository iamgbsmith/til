# Deploy Nginx Locally With Terraform

__Category: Terraform__

This TIL will deploy Nginx locally in Docker using Terraform.

Create a file called `main.tf` with the following content:

```json
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "~> 2.15.0"
    }
  }
}

provider "docker" {}

resource "docker_image" "nginx" {
  name         = "nginx:latest"
  keep_locally = false
}

resource "docker_container" "nginx" {
  image = docker_image.nginx.latest
  name  = "tutorial"
  ports {
    internal = 80
    external = 8000
  }
}
```

Initialize the project typing "yes" when prompted. 

If run for the first time, this command will also download a plugin that allows Terraform to interact with Docker:

```shell
terraform init
```

Create the execution plan to preview changes that Terraform will make:

```shell
terraform plan
``` 

Apply the plan to create the services:

```shell
terraform apply
``` 

Run `docker ps` to confirm the container is running. 

Test you can hit the Nginx server at http://localhost:8000

Stop the container and destroy the services. Type "yes" when prompted:

```shell
terraform destroy
```
