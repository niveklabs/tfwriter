# gridscale_snapshotschedule

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
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_snapshotschedule" {
  source = "./modules/gridscale/r/gridscale_snapshotschedule"

  # keep_snapshots - (required) is a type of number
  keep_snapshots = null
  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # next_runtime - (optional) is a type of string
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
variable "keep_snapshots" {
  description = "(required) - The amount of Snapshots to keep before overwriting the last created Snapshot"
  type        = number
}

variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object"
  type        = string
}

variable "next_runtime" {
  description = "(optional) - The date and time that the snapshot schedule will be run"
  type        = string
  default     = null
}

variable "run_interval" {
  description = "(required) - The interval at which the schedule will run (in minutes)"
  type        = number
}

variable "storage_uuid" {
  description = "(required) - Uuid of the storage used to create snapshots"
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
resource "gridscale_snapshotschedule" "this" {
  keep_snapshots = var.keep_snapshots
  labels         = var.labels
  name           = var.name
  next_runtime   = var.next_runtime
  run_interval   = var.run_interval
  storage_uuid   = var.storage_uuid

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
  value       = gridscale_snapshotschedule.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_snapshotschedule.this.create_time
}

output "id" {
  description = "returns a string"
  value       = gridscale_snapshotschedule.this.id
}

output "next_runtime_computed" {
  description = "returns a string"
  value       = gridscale_snapshotschedule.this.next_runtime_computed
}

output "snapshot" {
  description = "returns a set of object"
  value       = gridscale_snapshotschedule.this.snapshot
}

output "status" {
  description = "returns a string"
  value       = gridscale_snapshotschedule.this.status
}

output "this" {
  value = gridscale_snapshotschedule.this
}
```

[top](#index)