# mongodbatlas_cloud_provider_snapshot_backup_policy

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_cloud_provider_snapshot_backup_policy" {
  source = "./modules/mongodbatlas/r/mongodbatlas_cloud_provider_snapshot_backup_policy"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # project_id - (required) is a type of string
  project_id = null
  # reference_hour_of_day - (optional) is a type of number
  reference_hour_of_day = null
  # reference_minute_of_hour - (optional) is a type of number
  reference_minute_of_hour = null
  # restore_window_days - (optional) is a type of number
  restore_window_days = null
  # update_snapshots - (optional) is a type of bool
  update_snapshots = null

  policies = [{
    id = null
    policy_item = [{
      frequency_interval = null
      frequency_type     = null
      id                 = null
      retention_unit     = null
      retention_value    = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "reference_hour_of_day" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reference_minute_of_hour" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "restore_window_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "update_snapshots" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "policies" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      id = string
      policy_item = list(object(
        {
          frequency_interval = number
          frequency_type     = string
          id                 = string
          retention_unit     = string
          retention_value    = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_cloud_provider_snapshot_backup_policy" "this" {
  # cluster_name - (required) is a type of string
  cluster_name = var.cluster_name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # reference_hour_of_day - (optional) is a type of number
  reference_hour_of_day = var.reference_hour_of_day
  # reference_minute_of_hour - (optional) is a type of number
  reference_minute_of_hour = var.reference_minute_of_hour
  # restore_window_days - (optional) is a type of number
  restore_window_days = var.restore_window_days
  # update_snapshots - (optional) is a type of bool
  update_snapshots = var.update_snapshots

  dynamic "policies" {
    for_each = var.policies
    content {
      # id - (required) is a type of string
      id = policies.value["id"]

      dynamic "policy_item" {
        for_each = policies.value.policy_item
        content {
          # frequency_interval - (required) is a type of number
          frequency_interval = policy_item.value["frequency_interval"]
          # frequency_type - (required) is a type of string
          frequency_type = policy_item.value["frequency_type"]
          # id - (required) is a type of string
          id = policy_item.value["id"]
          # retention_unit - (required) is a type of string
          retention_unit = policy_item.value["retention_unit"]
          # retention_value - (required) is a type of number
          retention_value = policy_item.value["retention_value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_backup_policy.this.cluster_id
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_backup_policy.this.id
}

output "next_snapshot" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_backup_policy.this.next_snapshot
}

output "reference_hour_of_day" {
  description = "returns a number"
  value       = mongodbatlas_cloud_provider_snapshot_backup_policy.this.reference_hour_of_day
}

output "reference_minute_of_hour" {
  description = "returns a number"
  value       = mongodbatlas_cloud_provider_snapshot_backup_policy.this.reference_minute_of_hour
}

output "restore_window_days" {
  description = "returns a number"
  value       = mongodbatlas_cloud_provider_snapshot_backup_policy.this.restore_window_days
}

output "update_snapshots" {
  description = "returns a bool"
  value       = mongodbatlas_cloud_provider_snapshot_backup_policy.this.update_snapshots
}

output "this" {
  value = mongodbatlas_cloud_provider_snapshot_backup_policy.this
}
```

[top](#index)