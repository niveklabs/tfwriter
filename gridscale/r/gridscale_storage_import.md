# gridscale_storage_import

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
module "gridscale_storage_import" {
  source = "./modules/gridscale/r/gridscale_storage_import"

  # capacity - (optional) is a type of number
  capacity = null
  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # storage_backup_id - (required) is a type of string
  storage_backup_id = null
  # storage_type - (optional) is a type of string
  storage_type = null

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
  description = "(optional) - The capacity of a storage in GB."
  type        = number
  default     = null
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

variable "storage_backup_id" {
  description = "(required) - ID of the storage backup that will be used to create a new storage from."
  type        = string
}

variable "storage_type" {
  description = "(optional) - (one of storage, storage_high, storage_insane)"
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
resource "gridscale_storage_import" "this" {
  # capacity - (optional) is a type of number
  capacity = var.capacity
  # labels - (optional) is a type of set of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # storage_backup_id - (required) is a type of string
  storage_backup_id = var.storage_backup_id
  # storage_type - (optional) is a type of string
  storage_type = var.storage_type

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
output "capacity" {
  description = "returns a number"
  value       = gridscale_storage_import.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = gridscale_storage_import.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_storage_import.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_storage_import.this.current_price
}

output "id" {
  description = "returns a string"
  value       = gridscale_storage_import.this.id
}

output "last_used_template" {
  description = "returns a string"
  value       = gridscale_storage_import.this.last_used_template
}

output "license_product_no" {
  description = "returns a number"
  value       = gridscale_storage_import.this.license_product_no
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_storage_import.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_storage_import.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_storage_import.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_storage_import.this.location_uuid
}

output "parent_uuid" {
  description = "returns a string"
  value       = gridscale_storage_import.this.parent_uuid
}

output "status" {
  description = "returns a string"
  value       = gridscale_storage_import.this.status
}

output "storage_type" {
  description = "returns a string"
  value       = gridscale_storage_import.this.storage_type
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = gridscale_storage_import.this.usage_in_minutes
}

output "this" {
  value = gridscale_storage_import.this
}
```

[top](#index)