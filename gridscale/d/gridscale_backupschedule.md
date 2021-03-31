# gridscale_backupschedule

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
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_backupschedule" {
  source = "./modules/gridscale/d/gridscale_backupschedule"

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
  description = "(required) - Uuid of the storage used to create backups"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_backupschedule" "this" {
  resource_id  = var.resource_id
  storage_uuid = var.storage_uuid
}
```

[top](#index)

### Outputs

```terraform
output "active" {
  description = "returns a bool"
  value       = data.gridscale_backupschedule.this.active
}

output "change_time" {
  description = "returns a string"
  value       = data.gridscale_backupschedule.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_backupschedule.this.create_time
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_backupschedule.this.id
}

output "keep_backups" {
  description = "returns a number"
  value       = data.gridscale_backupschedule.this.keep_backups
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_backupschedule.this.name
}

output "next_runtime" {
  description = "returns a string"
  value       = data.gridscale_backupschedule.this.next_runtime
}

output "run_interval" {
  description = "returns a number"
  value       = data.gridscale_backupschedule.this.run_interval
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_backupschedule.this.status
}

output "storage_backups" {
  description = "returns a set of object"
  value       = data.gridscale_backupschedule.this.storage_backups
}

output "this" {
  value = gridscale_backupschedule.this
}
```

[top](#index)