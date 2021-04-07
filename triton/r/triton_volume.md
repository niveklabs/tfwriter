# triton_volume

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_volume" {
  source = "./modules/triton/r/triton_volume"

  # name - (optional) is a type of string
  name = null
  # networks - (optional) is a type of list of string
  networks = []
  # size - (optional) is a type of number
  size = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Friendly name for volume"
  type        = string
  default     = null
}

variable "networks" {
  description = "(optional) - Desired network IDs"
  type        = list(string)
  default     = null
}

variable "size" {
  description = "(optional) - The size of the volume (Mb)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Volume tags"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional) - Type of volume"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "triton_volume" "this" {
  # name - (optional) is a type of string
  name = var.name
  # networks - (optional) is a type of list of string
  networks = var.networks
  # size - (optional) is a type of number
  size = var.size
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "filesystem_path" {
  description = "returns a string"
  value       = triton_volume.this.filesystem_path
}

output "id" {
  description = "returns a string"
  value       = triton_volume.this.id
}

output "name" {
  description = "returns a string"
  value       = triton_volume.this.name
}

output "networks" {
  description = "returns a list of string"
  value       = triton_volume.this.networks
}

output "owner" {
  description = "returns a string"
  value       = triton_volume.this.owner
}

output "size" {
  description = "returns a number"
  value       = triton_volume.this.size
}

output "state" {
  description = "returns a string"
  value       = triton_volume.this.state
}

output "this" {
  value = triton_volume.this
}
```

[top](#index)