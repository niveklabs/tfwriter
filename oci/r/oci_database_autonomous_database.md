# oci_database_autonomous_database

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_database" {
  source = null

  # admin_password - (optional) is a type of string
  admin_password = null
  # are_primary_whitelisted_ips_used - (optional) is a type of bool
  are_primary_whitelisted_ips_used = null
  # autonomous_container_database_id - (optional) is a type of string
  autonomous_container_database_id = null
  # autonomous_database_backup_id - (optional) is a type of string
  autonomous_database_backup_id = null
  # autonomous_database_id - (optional) is a type of string
  autonomous_database_id = null
  # clone_type - (optional) is a type of string
  clone_type = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # cpu_core_count - (required) is a type of number
  cpu_core_count = null
  # data_safe_status - (optional) is a type of string
  data_safe_status = null
  # data_storage_size_in_tbs - (optional) is a type of number
  data_storage_size_in_tbs = null
  # db_name - (required) is a type of string
  db_name = null
  # db_version - (optional) is a type of string
  db_version = null
  # db_workload - (optional) is a type of string
  db_workload = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_access_control_enabled - (optional) is a type of bool
  is_access_control_enabled = null
  # is_auto_scaling_enabled - (optional) is a type of bool
  is_auto_scaling_enabled = null
  # is_data_guard_enabled - (optional) is a type of bool
  is_data_guard_enabled = null
  # is_dedicated - (optional) is a type of bool
  is_dedicated = null
  # is_free_tier - (optional) is a type of bool
  is_free_tier = null
  # is_preview_version_with_service_terms_accepted - (optional) is a type of bool
  is_preview_version_with_service_terms_accepted = null
  # is_refreshable_clone - (optional) is a type of bool
  is_refreshable_clone = null
  # license_model - (optional) is a type of string
  license_model = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # open_mode - (optional) is a type of string
  open_mode = null
  # operations_insights_status - (optional) is a type of string
  operations_insights_status = null
  # permission_level - (optional) is a type of string
  permission_level = null
  # private_endpoint_label - (optional) is a type of string
  private_endpoint_label = null
  # refreshable_mode - (optional) is a type of string
  refreshable_mode = null
  # rotate_key_trigger - (optional) is a type of bool
  rotate_key_trigger = null
  # source - (optional) is a type of string
  # source_id - (optional) is a type of string
  source_id = null
  # standby_whitelisted_ips - (optional) is a type of list of string
  standby_whitelisted_ips = []
  # state - (optional) is a type of string
  state = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # switchover_to - (optional) is a type of string
  switchover_to = null
  # timestamp - (optional) is a type of string
  timestamp = null
  # whitelisted_ips - (optional) is a type of set of string
  whitelisted_ips = []

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admin_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "are_primary_whitelisted_ips_used" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "autonomous_container_database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autonomous_database_backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autonomous_database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "clone_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "cpu_core_count" {
  description = "(required)"
  type        = number
}

variable "data_safe_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_storage_size_in_tbs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "db_name" {
  description = "(required)"
  type        = string
}

variable "db_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_workload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_access_control_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_auto_scaling_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_data_guard_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_dedicated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_free_tier" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_preview_version_with_service_terms_accepted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_refreshable_clone" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "license_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "open_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operations_insights_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permission_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_endpoint_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "refreshable_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rotate_key_trigger" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "standby_whitelisted_ips" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switchover_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timestamp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "whitelisted_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_autonomous_database" "this" {
  admin_password                                 = var.admin_password
  are_primary_whitelisted_ips_used               = var.are_primary_whitelisted_ips_used
  autonomous_container_database_id               = var.autonomous_container_database_id
  autonomous_database_backup_id                  = var.autonomous_database_backup_id
  autonomous_database_id                         = var.autonomous_database_id
  clone_type                                     = var.clone_type
  compartment_id                                 = var.compartment_id
  cpu_core_count                                 = var.cpu_core_count
  data_safe_status                               = var.data_safe_status
  data_storage_size_in_tbs                       = var.data_storage_size_in_tbs
  db_name                                        = var.db_name
  db_version                                     = var.db_version
  db_workload                                    = var.db_workload
  defined_tags                                   = var.defined_tags
  display_name                                   = var.display_name
  freeform_tags                                  = var.freeform_tags
  is_access_control_enabled                      = var.is_access_control_enabled
  is_auto_scaling_enabled                        = var.is_auto_scaling_enabled
  is_data_guard_enabled                          = var.is_data_guard_enabled
  is_dedicated                                   = var.is_dedicated
  is_free_tier                                   = var.is_free_tier
  is_preview_version_with_service_terms_accepted = var.is_preview_version_with_service_terms_accepted
  is_refreshable_clone                           = var.is_refreshable_clone
  license_model                                  = var.license_model
  nsg_ids                                        = var.nsg_ids
  open_mode                                      = var.open_mode
  operations_insights_status                     = var.operations_insights_status
  permission_level                               = var.permission_level
  private_endpoint_label                         = var.private_endpoint_label
  refreshable_mode                               = var.refreshable_mode
  rotate_key_trigger                             = var.rotate_key_trigger
  source                                         = var.source
  source_id                                      = var.source_id
  standby_whitelisted_ips                        = var.standby_whitelisted_ips
  state                                          = var.state
  subnet_id                                      = var.subnet_id
  switchover_to                                  = var.switchover_to
  timestamp                                      = var.timestamp
  whitelisted_ips                                = var.whitelisted_ips

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admin_password" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.admin_password
  sensitive   = true
}

output "apex_details" {
  description = "returns a list of object"
  value       = oci_database_autonomous_database.this.apex_details
}

output "are_primary_whitelisted_ips_used" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.are_primary_whitelisted_ips_used
}

output "autonomous_container_database_id" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.autonomous_container_database_id
}

output "autonomous_database_backup_id" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.autonomous_database_backup_id
}

output "autonomous_database_id" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.autonomous_database_id
}

output "available_upgrade_versions" {
  description = "returns a list of string"
  value       = oci_database_autonomous_database.this.available_upgrade_versions
}

output "backup_config" {
  description = "returns a list of object"
  value       = oci_database_autonomous_database.this.backup_config
}

output "clone_type" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.clone_type
}

output "connection_strings" {
  description = "returns a list of object"
  value       = oci_database_autonomous_database.this.connection_strings
}

output "connection_urls" {
  description = "returns a list of object"
  value       = oci_database_autonomous_database.this.connection_urls
}

output "data_safe_status" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.data_safe_status
}

output "data_storage_size_in_gb" {
  description = "returns a number"
  value       = oci_database_autonomous_database.this.data_storage_size_in_gb
}

output "data_storage_size_in_tbs" {
  description = "returns a number"
  value       = oci_database_autonomous_database.this.data_storage_size_in_tbs
}

output "db_version" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.db_version
}

output "db_workload" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.db_workload
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_database.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.display_name
}

output "failed_data_recovery_in_seconds" {
  description = "returns a number"
  value       = oci_database_autonomous_database.this.failed_data_recovery_in_seconds
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.id
}

output "infrastructure_type" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.infrastructure_type
}

output "is_access_control_enabled" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_access_control_enabled
}

output "is_auto_scaling_enabled" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_auto_scaling_enabled
}

output "is_data_guard_enabled" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_data_guard_enabled
}

output "is_dedicated" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_dedicated
}

output "is_free_tier" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_free_tier
}

output "is_preview" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_preview
}

output "is_preview_version_with_service_terms_accepted" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_preview_version_with_service_terms_accepted
}

output "is_refreshable_clone" {
  description = "returns a bool"
  value       = oci_database_autonomous_database.this.is_refreshable_clone
}

output "key_store_id" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.key_store_id
}

output "key_store_wallet_name" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.key_store_wallet_name
}

output "license_model" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.lifecycle_details
}

output "nsg_ids" {
  description = "returns a set of string"
  value       = oci_database_autonomous_database.this.nsg_ids
}

output "open_mode" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.open_mode
}

output "operations_insights_status" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.operations_insights_status
}

output "permission_level" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.permission_level
}

output "private_endpoint" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.private_endpoint
}

output "private_endpoint_ip" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.private_endpoint_ip
}

output "private_endpoint_label" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.private_endpoint_label
}

output "refreshable_mode" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.refreshable_mode
}

output "refreshable_status" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.refreshable_status
}

output "role" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.role
}

output "service_console_url" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.service_console_url
}

output "source" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.source
}

output "source_id" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.source_id
}

output "standby_db" {
  description = "returns a list of object"
  value       = oci_database_autonomous_database.this.standby_db
}

output "standby_whitelisted_ips" {
  description = "returns a list of string"
  value       = oci_database_autonomous_database.this.standby_whitelisted_ips
}

output "state" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.subnet_id
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_database.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_created
}

output "time_deletion_of_free_autonomous_database" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_deletion_of_free_autonomous_database
}

output "time_maintenance_begin" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_maintenance_begin
}

output "time_maintenance_end" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_maintenance_end
}

output "time_of_last_failover" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_of_last_failover
}

output "time_of_last_refresh" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_of_last_refresh
}

output "time_of_last_refresh_point" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_of_last_refresh_point
}

output "time_of_last_switchover" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_of_last_switchover
}

output "time_of_next_refresh" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_of_next_refresh
}

output "time_reclamation_of_free_autonomous_database" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.time_reclamation_of_free_autonomous_database
}

output "timestamp" {
  description = "returns a string"
  value       = oci_database_autonomous_database.this.timestamp
}

output "used_data_storage_size_in_tbs" {
  description = "returns a number"
  value       = oci_database_autonomous_database.this.used_data_storage_size_in_tbs
}

output "this" {
  value = oci_database_autonomous_database.this
}
```

[top](#index)