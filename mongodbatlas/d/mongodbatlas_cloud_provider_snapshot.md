# mongodbatlas_cloud_provider_snapshot

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
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_cloud_provider_snapshot" {
  source = "./modules/mongodbatlas/d/mongodbatlas_cloud_provider_snapshot"

  # cluster_name - (required) is a type of string
  cluster_name = null
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

### Datasource

```terraform
data "mongodbatlas_cloud_provider_snapshot" "this" {
  cluster_name = var.cluster_name
  project_id   = var.project_id
  snapshot_id  = var.snapshot_id
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.description
}

output "expires_at" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.id
}

output "master_key_uuid" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.master_key_uuid
}

output "mongod_version" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.mongod_version
}

output "snapshot_type" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.snapshot_type
}

output "status" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.status
}

output "storage_size_bytes" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.storage_size_bytes
}

output "type" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshot.this.type
}

output "this" {
  value = mongodbatlas_cloud_provider_snapshot.this
}
```

[top](#index)