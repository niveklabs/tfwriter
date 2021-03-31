# gridscale_storage

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_storage" {
  source = "./modules/gridscale/r/gridscale_storage"

  # capacity - (required) is a type of number
  capacity = null
  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # rollback_from_backup_uuid - (optional) is a type of string
  rollback_from_backup_uuid = null
  # storage_type - (optional) is a type of string
  storage_type = null

  template = [{
    hostname      = null
    password      = null
    password_type = null
    sshkeys       = []
    template_uuid = null
  }]

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
variable "capacity" {
  description = "(required) - The capacity of a storage in GB."
  type        = number
}

variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters."
  type        = string
}

variable "rollback_from_backup_uuid" {
  description = "(optional) - Rollback the storage from a specific storage backup."
  type        = string
  default     = null
}

variable "storage_type" {
  description = "(optional) - (one of storage, storage_high, storage_insane)"
  type        = string
  default     = null
}

variable "template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      hostname      = string
      password      = string
      password_type = string
      sshkeys       = list(string)
      template_uuid = string
    }
  ))
  default = []
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
resource "gridscale_storage" "this" {
  capacity                  = var.capacity
  labels                    = var.labels
  name                      = var.name
  rollback_from_backup_uuid = var.rollback_from_backup_uuid
  storage_type              = var.storage_type

  dynamic "template" {
    for_each = var.template
    content {
      hostname      = template.value["hostname"]
      password      = template.value["password"]
      password_type = template.value["password_type"]
      sshkeys       = template.value["sshkeys"]
      template_uuid = template.value["template_uuid"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = gridscale_storage.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_storage.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_storage.this.current_price
}

output "id" {
  description = "returns a string"
  value       = gridscale_storage.this.id
}

output "last_used_template" {
  description = "returns a string"
  value       = gridscale_storage.this.last_used_template
}

output "license_product_no" {
  description = "returns a number"
  value       = gridscale_storage.this.license_product_no
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_storage.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_storage.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_storage.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_storage.this.location_uuid
}

output "parent_uuid" {
  description = "returns a string"
  value       = gridscale_storage.this.parent_uuid
}

output "status" {
  description = "returns a string"
  value       = gridscale_storage.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = gridscale_storage.this.usage_in_minutes
}

output "this" {
  value = gridscale_storage.this
}
```

[top](#index)