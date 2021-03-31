# mongodbatlas_cluster

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
module "mongodbatlas_cluster" {
  source = "./modules/mongodbatlas/r/mongodbatlas_cluster"

  # auto_scaling_compute_enabled - (optional) is a type of bool
  auto_scaling_compute_enabled = null
  # auto_scaling_compute_scale_down_enabled - (optional) is a type of bool
  auto_scaling_compute_scale_down_enabled = null
  # auto_scaling_disk_gb_enabled - (optional) is a type of bool
  auto_scaling_disk_gb_enabled = null
  # backing_provider_name - (optional) is a type of string
  backing_provider_name = null
  # backup_enabled - (optional) is a type of bool
  backup_enabled = null
  # bi_connector - (optional) is a type of map of string
  bi_connector = {}
  # cluster_type - (optional) is a type of string
  cluster_type = null
  # disk_size_gb - (optional) is a type of number
  disk_size_gb = null
  # encryption_at_rest_provider - (optional) is a type of string
  encryption_at_rest_provider = null
  # mongo_db_major_version - (optional) is a type of string
  mongo_db_major_version = null
  # name - (required) is a type of string
  name = null
  # num_shards - (optional) is a type of number
  num_shards = null
  # pit_enabled - (optional) is a type of bool
  pit_enabled = null
  # project_id - (required) is a type of string
  project_id = null
  # provider_auto_scaling_compute_max_instance_size - (optional) is a type of string
  provider_auto_scaling_compute_max_instance_size = null
  # provider_auto_scaling_compute_min_instance_size - (optional) is a type of string
  provider_auto_scaling_compute_min_instance_size = null
  # provider_backup_enabled - (optional) is a type of bool
  provider_backup_enabled = null
  # provider_disk_iops - (optional) is a type of number
  provider_disk_iops = null
  # provider_disk_type_name - (optional) is a type of string
  provider_disk_type_name = null
  # provider_encrypt_ebs_volume - (optional) is a type of bool
  provider_encrypt_ebs_volume = null
  # provider_instance_size_name - (required) is a type of string
  provider_instance_size_name = null
  # provider_name - (required) is a type of string
  provider_name = null
  # provider_region_name - (optional) is a type of string
  provider_region_name = null
  # provider_volume_type - (optional) is a type of string
  provider_volume_type = null
  # replication_factor - (optional) is a type of number
  replication_factor = null

  advanced_configuration = [{
    fail_index_key_too_long              = null
    javascript_enabled                   = null
    minimum_enabled_tls_protocol         = null
    no_table_scan                        = null
    oplog_size_mb                        = null
    sample_refresh_interval_bi_connector = null
    sample_size_bi_connector             = null
  }]

  labels = [{
    key   = null
    value = null
  }]

  replication_specs = [{
    id         = null
    num_shards = null
    regions_config = [{
      analytics_nodes = null
      electable_nodes = null
      priority        = null
      read_only_nodes = null
      region_name     = null
    }]
    zone_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_scaling_compute_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_scaling_compute_scale_down_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_scaling_disk_gb_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "backing_provider_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bi_connector" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cluster_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_size_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "encryption_at_rest_provider" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mongo_db_major_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "num_shards" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pit_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "provider_auto_scaling_compute_max_instance_size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_auto_scaling_compute_min_instance_size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_backup_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "provider_disk_iops" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "provider_disk_type_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_encrypt_ebs_volume" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "provider_instance_size_name" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(required)"
  type        = string
}

variable "provider_region_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_volume_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replication_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "advanced_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      fail_index_key_too_long              = bool
      javascript_enabled                   = bool
      minimum_enabled_tls_protocol         = string
      no_table_scan                        = bool
      oplog_size_mb                        = number
      sample_refresh_interval_bi_connector = number
      sample_size_bi_connector             = number
    }
  ))
  default = []
}

variable "labels" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "replication_specs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id         = string
      num_shards = number
      regions_config = set(object(
        {
          analytics_nodes = number
          electable_nodes = number
          priority        = number
          read_only_nodes = number
          region_name     = string
        }
      ))
      zone_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_cluster" "this" {
  auto_scaling_compute_enabled                    = var.auto_scaling_compute_enabled
  auto_scaling_compute_scale_down_enabled         = var.auto_scaling_compute_scale_down_enabled
  auto_scaling_disk_gb_enabled                    = var.auto_scaling_disk_gb_enabled
  backing_provider_name                           = var.backing_provider_name
  backup_enabled                                  = var.backup_enabled
  bi_connector                                    = var.bi_connector
  cluster_type                                    = var.cluster_type
  disk_size_gb                                    = var.disk_size_gb
  encryption_at_rest_provider                     = var.encryption_at_rest_provider
  mongo_db_major_version                          = var.mongo_db_major_version
  name                                            = var.name
  num_shards                                      = var.num_shards
  pit_enabled                                     = var.pit_enabled
  project_id                                      = var.project_id
  provider_auto_scaling_compute_max_instance_size = var.provider_auto_scaling_compute_max_instance_size
  provider_auto_scaling_compute_min_instance_size = var.provider_auto_scaling_compute_min_instance_size
  provider_backup_enabled                         = var.provider_backup_enabled
  provider_disk_iops                              = var.provider_disk_iops
  provider_disk_type_name                         = var.provider_disk_type_name
  provider_encrypt_ebs_volume                     = var.provider_encrypt_ebs_volume
  provider_instance_size_name                     = var.provider_instance_size_name
  provider_name                                   = var.provider_name
  provider_region_name                            = var.provider_region_name
  provider_volume_type                            = var.provider_volume_type
  replication_factor                              = var.replication_factor

  dynamic "advanced_configuration" {
    for_each = var.advanced_configuration
    content {
      fail_index_key_too_long              = advanced_configuration.value["fail_index_key_too_long"]
      javascript_enabled                   = advanced_configuration.value["javascript_enabled"]
      minimum_enabled_tls_protocol         = advanced_configuration.value["minimum_enabled_tls_protocol"]
      no_table_scan                        = advanced_configuration.value["no_table_scan"]
      oplog_size_mb                        = advanced_configuration.value["oplog_size_mb"]
      sample_refresh_interval_bi_connector = advanced_configuration.value["sample_refresh_interval_bi_connector"]
      sample_size_bi_connector             = advanced_configuration.value["sample_size_bi_connector"]
    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      key   = labels.value["key"]
      value = labels.value["value"]
    }
  }

  dynamic "replication_specs" {
    for_each = var.replication_specs
    content {
      id         = replication_specs.value["id"]
      num_shards = replication_specs.value["num_shards"]
      zone_name  = replication_specs.value["zone_name"]

      dynamic "regions_config" {
        for_each = replication_specs.value.regions_config
        content {
          analytics_nodes = regions_config.value["analytics_nodes"]
          electable_nodes = regions_config.value["electable_nodes"]
          priority        = regions_config.value["priority"]
          read_only_nodes = regions_config.value["read_only_nodes"]
          region_name     = regions_config.value["region_name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_scaling_compute_enabled" {
  description = "returns a bool"
  value       = mongodbatlas_cluster.this.auto_scaling_compute_enabled
}

output "auto_scaling_compute_scale_down_enabled" {
  description = "returns a bool"
  value       = mongodbatlas_cluster.this.auto_scaling_compute_scale_down_enabled
}

output "backing_provider_name" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.backing_provider_name
}

output "bi_connector" {
  description = "returns a map of string"
  value       = mongodbatlas_cluster.this.bi_connector
}

output "cluster_id" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.cluster_id
}

output "cluster_type" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.cluster_type
}

output "connection_strings" {
  description = "returns a list of object"
  value       = mongodbatlas_cluster.this.connection_strings
}

output "container_id" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.container_id
}

output "disk_size_gb" {
  description = "returns a number"
  value       = mongodbatlas_cluster.this.disk_size_gb
}

output "encryption_at_rest_provider" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.encryption_at_rest_provider
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.id
}

output "mongo_db_major_version" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.mongo_db_major_version
}

output "mongo_db_version" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.mongo_db_version
}

output "mongo_uri" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.mongo_uri
}

output "mongo_uri_updated" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.mongo_uri_updated
}

output "mongo_uri_with_options" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.mongo_uri_with_options
}

output "paused" {
  description = "returns a bool"
  value       = mongodbatlas_cluster.this.paused
}

output "pit_enabled" {
  description = "returns a bool"
  value       = mongodbatlas_cluster.this.pit_enabled
}

output "provider_auto_scaling_compute_max_instance_size" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.provider_auto_scaling_compute_max_instance_size
}

output "provider_auto_scaling_compute_min_instance_size" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.provider_auto_scaling_compute_min_instance_size
}

output "provider_disk_iops" {
  description = "returns a number"
  value       = mongodbatlas_cluster.this.provider_disk_iops
}

output "provider_disk_type_name" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.provider_disk_type_name
}

output "provider_encrypt_ebs_volume" {
  description = "returns a bool"
  value       = mongodbatlas_cluster.this.provider_encrypt_ebs_volume
}

output "provider_region_name" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.provider_region_name
}

output "provider_volume_type" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.provider_volume_type
}

output "replication_factor" {
  description = "returns a number"
  value       = mongodbatlas_cluster.this.replication_factor
}

output "snapshot_backup_policy" {
  description = "returns a list of object"
  value       = mongodbatlas_cluster.this.snapshot_backup_policy
}

output "srv_address" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.srv_address
}

output "state_name" {
  description = "returns a string"
  value       = mongodbatlas_cluster.this.state_name
}

output "this" {
  value = mongodbatlas_cluster.this
}
```

[top](#index)