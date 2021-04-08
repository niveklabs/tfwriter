# vra_block_device_snapshot

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_block_device_snapshot" {
  source = "./modules/vra/r/vra_block_device_snapshot"

  # block_device_id - (required) is a type of string
  block_device_id = null
  # description - (optional) is a type of string
  description = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "block_device_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_block_device_snapshot" "this" {
  # block_device_id - (required) is a type of string
  block_device_id = var.block_device_id
  # description - (optional) is a type of string
  description = var.description

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = vra_block_device_snapshot.this.created_at
}

output "id" {
  description = "returns a string"
  value       = vra_block_device_snapshot.this.id
}

output "is_current" {
  description = "returns a bool"
  value       = vra_block_device_snapshot.this.is_current
}

output "links" {
  description = "returns a set of object"
  value       = vra_block_device_snapshot.this.links
}

output "name" {
  description = "returns a string"
  value       = vra_block_device_snapshot.this.name
}

output "org_id" {
  description = "returns a string"
  value       = vra_block_device_snapshot.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_block_device_snapshot.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_block_device_snapshot.this.updated_at
}

output "this" {
  value = vra_block_device_snapshot.this
}
```

[top](#index)