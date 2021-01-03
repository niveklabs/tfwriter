# docker_volume

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
module "docker_volume" {
  source = "./modules/docker/r/docker_volume"

  # driver - (optional) is a type of string
  driver = null
  # driver_opts - (optional) is a type of map of string
  driver_opts = {}
  # name - (optional) is a type of string
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
variable "driver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "driver_opts" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "docker_volume" "this" {
  driver      = var.driver
  driver_opts = var.driver_opts
  name        = var.name

  dynamic "labels" {
    for_each = var.labels
    content {
      label = labels.value["label"]
      value = labels.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "driver" {
  description = "returns a string"
  value       = docker_volume.this.driver
}

output "id" {
  description = "returns a string"
  value       = docker_volume.this.id
}

output "mountpoint" {
  description = "returns a string"
  value       = docker_volume.this.mountpoint
}

output "name" {
  description = "returns a string"
  value       = docker_volume.this.name
}

output "this" {
  value = docker_volume.this
}
```

[top](#index)