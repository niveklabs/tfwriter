# gridscale_snapshotschedule

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/gridscale/d/gridscale_snapshotschedule"

  # resource_id - (required) is a type of string
  resource_id = null
  # storage_uuid - (required) is a type of string
  storage_uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}

variable "storage_uuid" {
  description = "(required) - Uuid of the storage used to create snapshots"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_snapshotschedule" "this" {
  resource_id  = var.resource_id
  storage_uuid = var.storage_uuid
}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = data.gridscale_snapshotschedule.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_snapshotschedule.this.create_time
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_snapshotschedule.this.id
}

output "keep_snapshots" {
  description = "returns a number"
  value       = data.gridscale_snapshotschedule.this.keep_snapshots
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_snapshotschedule.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_snapshotschedule.this.name
}

output "next_runtime" {
  description = "returns a string"
  value       = data.gridscale_snapshotschedule.this.next_runtime
}

output "run_interval" {
  description = "returns a number"
  value       = data.gridscale_snapshotschedule.this.run_interval
}

output "snapshot" {
  description = "returns a set of object"
  value       = data.gridscale_snapshotschedule.this.snapshot
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_snapshotschedule.this.status
}

output "this" {
  value = gridscale_snapshotschedule.this
}
```

[top](#index)