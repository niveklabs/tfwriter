# docker_secret

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
module "docker_secret" {
  source = "./modules/docker/r/docker_secret"

  # data - (required) is a type of string
  data = null
  # name - (required) is a type of string
  name = null

  labels = [{
    label = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data" {
  description = "(required) - Base64-url-safe-encoded secret data"
  type        = string
}

variable "name" {
  description = "(required) - User-defined name of the secret"
  type        = string
}

variable "labels" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      label = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "docker_secret" "this" {
  # data - (required) is a type of string
  data = var.data
  # name - (required) is a type of string
  name = var.name

  dynamic "labels" {
    for_each = var.labels
    content {
      # label - (required) is a type of string
      label = labels.value["label"]
      # value - (required) is a type of string
      value = labels.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = docker_secret.this.id
}

output "this" {
  value = docker_secret.this
}
```

[top](#index)