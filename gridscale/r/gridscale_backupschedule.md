# gridscale_backupschedule

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
module "gridscale_backupschedule" {
  source = "./modules/gridscale/r/gridscale_backupschedule"

  # active - (required) is a type of bool
  active = null
  # keep_backups - (required) is a type of number
  keep_backups = null
  # name - (required) is a type of string
  name = null
  # next_runtime - (required) is a type of string
  next_runtime = null
  # run_interval - (required) is a type of number
  run_interval = null
  # storage_uuid - (required) is a type of string
  storage_uuid = null

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
variable "active" {
  description = "(required) - The status of the schedule active or not"
  type        = bool
}

variable "keep_backups" {
  description = "(required) - The amount of storage backups to keep before overwriting the last created backup"
  type        = number
}

variable "name" {
  description = "(required) - The human-readable name of the object"
  type        = string
}

variable "next_runtime" {
  description = "(required) - The date and time that the storage backup schedule will be run. Format: \"2006-01-02 15:04:05\""
  type        = string
}

variable "run_interval" {
  description = "(required) - The interval at which the schedule will run (in minutes)"
  type        = number
}

variable "storage_uuid" {
  description = "(required) - Uuid of the storage used to create storage backups"
  type        = string
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
resource "gridscale_backupschedule" "this" {
  active       = var.active
  keep_backups = var.keep_backups
  name         = var.name
  next_runtime = var.next_runtime
  run_interval = var.run_interval
  storage_uuid = var.storage_uuid

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
  value       = gridscale_backupschedule.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_backupschedule.this.create_time
}

output "id" {
  description = "returns a string"
  value       = gridscale_backupschedule.this.id
}

output "next_runtime_computed" {
  description = "returns a string"
  value       = gridscale_backupschedule.this.next_runtime_computed
}

output "status" {
  description = "returns a string"
  value       = gridscale_backupschedule.this.status
}

output "storage_backups" {
  description = "returns a set of object"
  value       = gridscale_backupschedule.this.storage_backups
}

output "this" {
  value = gridscale_backupschedule.this
}
```

[top](#index)