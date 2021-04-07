# mongodbatlas_cloud_provider_snapshot

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
module "mongodbatlas_cloud_provider_snapshot" {
  source = "./modules/mongodbatlas/r/mongodbatlas_cloud_provider_snapshot"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # description - (required) is a type of string
  description = null
  # project_id - (required) is a type of string
  project_id = null
  # retention_in_days - (required) is a type of number
  retention_in_days = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "retention_in_days" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_cloud_provider_snapshot" "this" {
  # cluster_name - (required) is a type of string
  cluster_name = var.cluster_name
  # description - (required) is a type of string
  description = var.description
  # project_id - (required) is a type of string
  project_id = var.project_id
  # retention_in_days - (required) is a type of number
  retention_in_days = var.retention_in_days
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.created_at
}

output "expires_at" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.id
}

output "master_key_uuid" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.master_key_uuid
}

output "mongod_version" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.mongod_version
}

output "snapshot_id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.snapshot_id
}

output "snapshot_type" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.snapshot_type
}

output "status" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.status
}

output "storage_size_bytes" {
  description = "returns a number"
  value       = mongodbatlas_cloud_provider_snapshot.this.storage_size_bytes
}

output "type" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_snapshot.this.type
}

output "this" {
  value = mongodbatlas_cloud_provider_snapshot.this
}
```

[top](#index)