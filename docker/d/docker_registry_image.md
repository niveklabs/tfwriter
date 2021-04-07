# docker_registry_image

[back](../docker.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    docker = ">= 2.7.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "docker_registry_image" {
  source = "./modules/docker/d/docker_registry_image"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "docker_registry_image" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.docker_registry_image.this.id
}

output "sha256_digest" {
  description = "returns a string"
  value       = data.docker_registry_image.this.sha256_digest
}

output "this" {
  value = docker_registry_image.this
}
```

[top](#index)