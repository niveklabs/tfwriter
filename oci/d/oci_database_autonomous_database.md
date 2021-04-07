# oci_database_autonomous_database

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_database" {
  source = "./modules/oci/d/oci_database_autonomous_database"

  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_database_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_database" "this" {
  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = var.autonomous_database_id
}
```

[top](#index)

### Outputs

```terraform
output "admin_password" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.admin_password
  sensitive   = true
}

output "apex_details" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_database.this.apex_details
}

output "are_primary_whitelisted_ips_used" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.are_primary_whitelisted_ips_used
}

output "autonomous_container_database_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.autonomous_container_database_id
}

output "autonomous_database_backup_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.autonomous_database_backup_id
}

output "available_upgrade_versions" {
  description = "returns a list of string"
  value       = data.oci_database_autonomous_database.this.available_upgrade_versions
}

output "backup_config" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_database.this.backup_config
}

output "clone_type" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.clone_type
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.compartment_id
}

output "connection_strings" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_database.this.connection_strings
}

output "connection_urls" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_database.this.connection_urls
}

output "cpu_core_count" {
  description = "returns a number"
  value       = data.oci_database_autonomous_database.this.cpu_core_count
}

output "data_safe_status" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.data_safe_status
}

output "data_storage_size_in_gb" {
  description = "returns a number"
  value       = data.oci_database_autonomous_database.this.data_storage_size_in_gb
}

output "data_storage_size_in_tbs" {
  description = "returns a number"
  value       = data.oci_database_autonomous_database.this.data_storage_size_in_tbs
}

output "db_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.db_name
}

output "db_version" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.db_version
}

output "db_workload" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.db_workload
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_autonomous_database.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.display_name
}

output "failed_data_recovery_in_seconds" {
  description = "returns a number"
  value       = data.oci_database_autonomous_database.this.failed_data_recovery_in_seconds
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_autonomous_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.id
}

output "infrastructure_type" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.infrastructure_type
}

output "is_access_control_enabled" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_access_control_enabled
}

output "is_auto_scaling_enabled" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_auto_scaling_enabled
}

output "is_data_guard_enabled" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_data_guard_enabled
}

output "is_dedicated" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_dedicated
}

output "is_free_tier" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_free_tier
}

output "is_preview" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_preview
}

output "is_preview_version_with_service_terms_accepted" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_preview_version_with_service_terms_accepted
}

output "is_refreshable_clone" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.is_refreshable_clone
}

output "key_store_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.key_store_id
}

output "key_store_wallet_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.key_store_wallet_name
}

output "license_model" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.lifecycle_details
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_database_autonomous_database.this.nsg_ids
}

output "open_mode" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.open_mode
}

output "operations_insights_status" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.operations_insights_status
}

output "permission_level" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.permission_level
}

output "private_endpoint" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.private_endpoint
}

output "private_endpoint_ip" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.private_endpoint_ip
}

output "private_endpoint_label" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.private_endpoint_label
}

output "refreshable_mode" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.refreshable_mode
}

output "refreshable_status" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.refreshable_status
}

output "role" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.role
}

output "rotate_key_trigger" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database.this.rotate_key_trigger
}

output "service_console_url" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.service_console_url
}

output "source" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.source
}

output "source_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.source_id
}

output "standby_db" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_database.this.standby_db
}

output "standby_whitelisted_ips" {
  description = "returns a list of string"
  value       = data.oci_database_autonomous_database.this.standby_whitelisted_ips
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.subnet_id
}

output "switchover_to" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.switchover_to
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_database_autonomous_database.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_created
}

output "time_deletion_of_free_autonomous_database" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_deletion_of_free_autonomous_database
}

output "time_maintenance_begin" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_maintenance_begin
}

output "time_maintenance_end" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_maintenance_end
}

output "time_of_last_failover" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_of_last_failover
}

output "time_of_last_refresh" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_of_last_refresh
}

output "time_of_last_refresh_point" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_of_last_refresh_point
}

output "time_of_last_switchover" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_of_last_switchover
}

output "time_of_next_refresh" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_of_next_refresh
}

output "time_reclamation_of_free_autonomous_database" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.time_reclamation_of_free_autonomous_database
}

output "timestamp" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database.this.timestamp
}

output "used_data_storage_size_in_tbs" {
  description = "returns a number"
  value       = data.oci_database_autonomous_database.this.used_data_storage_size_in_tbs
}

output "whitelisted_ips" {
  description = "returns a list of string"
  value       = data.oci_database_autonomous_database.this.whitelisted_ips
}

output "this" {
  value = oci_database_autonomous_database.this
}
```

[top](#index)