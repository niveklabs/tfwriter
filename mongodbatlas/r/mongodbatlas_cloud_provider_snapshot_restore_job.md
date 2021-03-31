# mongodbatlas_cloud_provider_snapshot_restore_job

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
module "mongodbatlas_cloud_provider_snapshot_restore_job" {
  source = "./modules/mongodbatlas/r/mongodbatlas_cloud_provider_snapshot_restore_job"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # delivery_type - (required) is a type of map of string
  delivery_type = {}
  # project_id - (required) is a type of string
  project_id = null
  # snapshot_id - (required) is a type of string
  snapshot_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "delivery_type" {
  description = "(required)"
  type        = map(string)
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "snapshot_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_cloud_provider_snapshot_restore_job" "this" {
  cluster_name  = var.cluster_name
  delivery_type = var.delivery_type
  project_id    = var.project_id
  snapshot_id   = var.snapshot_id
}
```

[top](#index)

### Outputs

```terraform
output "cancelled" {
  description = "returns a bool"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.cancelled
}

output "created_at" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.created_at
}

output "delivery_url" {
  description = "returns a list of string"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.delivery_url
}

output "expired" {
  description = "returns a bool"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.expired
}

output "expires_at" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.expires_at
}

output "finished_at" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.finished_at
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.id
}

output "snapshot_restore_job_id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.snapshot_restore_job_id
}

output "timestamp" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot_restore_job.this.timestamp
}

output "this" {
  value = mongodbatlas_cloud_provider_snapshot_restore_job.this
}
```

[top](#index)