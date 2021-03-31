# mongodbatlas_cloud_provider_snapshot_backup_policy

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/mongodbatlas/d/mongodbatlas_cloud_provider_snapshot_backup_policy"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # project_id - (required) is a type of string
  project_id = null
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
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_cloud_provider_snapshot_backup_policy" "this" {
  cluster_name = var.cluster_name
  project_id   = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "cluster_id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.cluster_id
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.id
}

output "next_snapshot" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.next_snapshot
}

output "policies" {
  description = "returns a list of object"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.policies
}

output "reference_hour_of_day" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.reference_hour_of_day
}

output "reference_minute_of_hour" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.reference_minute_of_hour
}

output "restore_window_days" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.restore_window_days
}

output "update_snapshots" {
  description = "returns a bool"
  value       = data.mongodbatlas_cloud_provider_snapshot_backup_policy.this.update_snapshots
}

output "this" {
  value = mongodbatlas_cloud_provider_snapshot_backup_policy.this
}
```

[top](#index)