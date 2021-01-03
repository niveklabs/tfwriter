# docker_config

[back](../docker.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "docker_config" {
  source = "./modules/docker/r/docker_config"

  # data - (required) is a type of string
  data = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "data" {
  description = "(required) - Base64-url-safe-encoded config data"
  type        = string
}

variable "name" {
  description = "(required) - User-defined name of the config"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "docker_config" "this" {
  data = var.data
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = docker_config.this.id
}

output "this" {
  value = docker_config.this
}
```

[top](#index)