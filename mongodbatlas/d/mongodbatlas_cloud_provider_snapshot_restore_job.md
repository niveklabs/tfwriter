# mongodbatlas_cloud_provider_snapshot_restore_job

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
module "mongodbatlas_cloud_provider_snapshot_restore_job" {
  source = "./modules/mongodbatlas/d/mongodbatlas_cloud_provider_snapshot_restore_job"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # job_id - (required) is a type of string
  job_id = null
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

variable "job_id" {
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
data "mongodbatlas_cloud_provider_snapshot_restore_job" "this" {
  # cluster_name - (required) is a type of string
  cluster_name = var.cluster_name
  # job_id - (required) is a type of string
  job_id = var.job_id
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "cancelled" {
  description = "returns a bool"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.cancelled
}

output "created_at" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.created_at
}

output "delivery_type" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.delivery_type
}

output "delivery_url" {
  description = "returns a list of string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.delivery_url
}

output "expired" {
  description = "returns a bool"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.expired
}

output "expires_at" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.expires_at
}

output "finished_at" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.finished_at
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.id
}

output "oplog_inc" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.oplog_inc
}

output "oplog_ts" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.oplog_ts
}

output "point_in_time_utc_seconds" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.point_in_time_utc_seconds
}

output "snapshot_id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.snapshot_id
}

output "target_cluster_name" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.target_cluster_name
}

output "target_project_id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.target_project_id
}

output "timestamp" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot_restore_job.this.timestamp
}

output "this" {
  value = mongodbatlas_cloud_provider_snapshot_restore_job.this
}
```

[top](#index)