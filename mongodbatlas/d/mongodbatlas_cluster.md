# mongodbatlas_cluster

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
module "mongodbatlas_cluster" {
  source = "./modules/mongodbatlas/d/mongodbatlas_cluster"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
data "mongodbatlas_cluster" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "auto_scaling_compute_enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.auto_scaling_compute_enabled
}

output "auto_scaling_compute_scale_down_enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.auto_scaling_compute_scale_down_enabled
}

output "auto_scaling_disk_gb_enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.auto_scaling_disk_gb_enabled
}

output "backing_provider_name" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.backing_provider_name
}

output "backup_enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.backup_enabled
}

output "bi_connector" {
  description = "returns a map of string"
  value       = data.mongodbatlas_cluster.this.bi_connector
}

output "cluster_type" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.cluster_type
}

output "connection_strings" {
  description = "returns a list of object"
  value       = data.mongodbatlas_cluster.this.connection_strings
}

output "container_id" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.container_id
}

output "disk_size_gb" {
  description = "returns a number"
  value       = data.mongodbatlas_cluster.this.disk_size_gb
}

output "encryption_at_rest_provider" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.encryption_at_rest_provider
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.id
}

output "labels" {
  description = "returns a set of object"
  value       = data.mongodbatlas_cluster.this.labels
}

output "mongo_db_major_version" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.mongo_db_major_version
}

output "mongo_db_version" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.mongo_db_version
}

output "mongo_uri" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.mongo_uri
}

output "mongo_uri_updated" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.mongo_uri_updated
}

output "mongo_uri_with_options" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.mongo_uri_with_options
}

output "num_shards" {
  description = "returns a number"
  value       = data.mongodbatlas_cluster.this.num_shards
}

output "paused" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.paused
}

output "pit_enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.pit_enabled
}

output "provider_auto_scaling_compute_max_instance_size" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.provider_auto_scaling_compute_max_instance_size
}

output "provider_auto_scaling_compute_min_instance_size" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.provider_auto_scaling_compute_min_instance_size
}

output "provider_backup_enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.provider_backup_enabled
}

output "provider_disk_iops" {
  description = "returns a number"
  value       = data.mongodbatlas_cluster.this.provider_disk_iops
}

output "provider_disk_type_name" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.provider_disk_type_name
}

output "provider_encrypt_ebs_volume" {
  description = "returns a bool"
  value       = data.mongodbatlas_cluster.this.provider_encrypt_ebs_volume
}

output "provider_instance_size_name" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.provider_instance_size_name
}

output "provider_name" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.provider_name
}

output "provider_region_name" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.provider_region_name
}

output "provider_volume_type" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.provider_volume_type
}

output "replication_factor" {
  description = "returns a number"
  value       = data.mongodbatlas_cluster.this.replication_factor
}

output "replication_specs" {
  description = "returns a list of object"
  value       = data.mongodbatlas_cluster.this.replication_specs
}

output "snapshot_backup_policy" {
  description = "returns a list of object"
  value       = data.mongodbatlas_cluster.this.snapshot_backup_policy
}

output "srv_address" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.srv_address
}

output "state_name" {
  description = "returns a string"
  value       = data.mongodbatlas_cluster.this.state_name
}

output "this" {
  value = mongodbatlas_cluster.this
}
```

[top](#index)