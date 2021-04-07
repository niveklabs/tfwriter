# gridscale_snapshot

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
module "gridscale_snapshot" {
  source = "./modules/gridscale/r/gridscale_snapshot"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # storage_uuid - (required) is a type of string
  storage_uuid = null

  object_storage_export = [{
    access_key = null
    bucket     = null
    host       = null
    object     = null
    private    = null
    secret_key = null
    status     = null
  }]

  rollback = [{
    id            = null
    rollback_time = null
    status        = null
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
variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object"
  type        = string
}

variable "storage_uuid" {
  description = "(required) - Uuid of the storage used to create this snapshot"
  type        = string
}

variable "object_storage_export" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key = string
      bucket     = string
      host       = string
      object     = string
      private    = bool
      secret_key = string
      status     = string
    }
  ))
  default = []
}

variable "rollback" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id            = string
      rollback_time = string
      status        = string
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
resource "gridscale_snapshot" "this" {
  # labels - (optional) is a type of set of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # storage_uuid - (required) is a type of string
  storage_uuid = var.storage_uuid

  dynamic "object_storage_export" {
    for_each = var.object_storage_export
    content {
      # access_key - (required) is a type of string
      access_key = object_storage_export.value["access_key"]
      # bucket - (required) is a type of string
      bucket = object_storage_export.value["bucket"]
      # host - (required) is a type of string
      host = object_storage_export.value["host"]
      # object - (required) is a type of string
      object = object_storage_export.value["object"]
      # private - (required) is a type of bool
      private = object_storage_export.value["private"]
      # secret_key - (required) is a type of string
      secret_key = object_storage_export.value["secret_key"]
    }
  }

  dynamic "rollback" {
    for_each = var.rollback
    content {
      # id - (required) is a type of string
      id = rollback.value["id"]
    }
  }

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
  value       = gridscale_snapshot.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = gridscale_snapshot.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_snapshot.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_snapshot.this.current_price
}

output "id" {
  description = "returns a string"
  value       = gridscale_snapshot.this.id
}

output "license_product_no" {
  description = "returns a number"
  value       = gridscale_snapshot.this.license_product_no
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_snapshot.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_snapshot.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_snapshot.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_snapshot.this.location_uuid
}

output "status" {
  description = "returns a string"
  value       = gridscale_snapshot.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = gridscale_snapshot.this.usage_in_minutes
}

output "this" {
  value = gridscale_snapshot.this
}
```

[top](#index)