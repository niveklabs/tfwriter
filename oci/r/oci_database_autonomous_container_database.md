# oci_database_autonomous_container_database

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_container_database" {
  source = "./modules/oci/r/oci_database_autonomous_container_database"

  # autonomous_exadata_infrastructure_id - (optional) is a type of string
  autonomous_exadata_infrastructure_id = null
  # autonomous_vm_cluster_id - (optional) is a type of string
  autonomous_vm_cluster_id = null
  # compartment_id - (optional) is a type of string
  compartment_id = null
  # db_unique_name - (optional) is a type of string
  db_unique_name = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # key_store_id - (optional) is a type of string
  key_store_id = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # patch_model - (required) is a type of string
  patch_model = null
  # peer_autonomous_container_database_compartment_id - (optional) is a type of string
  peer_autonomous_container_database_compartment_id = null
  # peer_autonomous_container_database_display_name - (optional) is a type of string
  peer_autonomous_container_database_display_name = null
  # peer_autonomous_exadata_infrastructure_id - (optional) is a type of string
  peer_autonomous_exadata_infrastructure_id = null
  # peer_autonomous_vm_cluster_id - (optional) is a type of string
  peer_autonomous_vm_cluster_id = null
  # peer_db_unique_name - (optional) is a type of string
  peer_db_unique_name = null
  # protection_mode - (optional) is a type of string
  protection_mode = null
  # rotate_key_trigger - (optional) is a type of bool
  rotate_key_trigger = null
  # service_level_agreement_type - (optional) is a type of string
  service_level_agreement_type = null
  # standby_maintenance_buffer_in_days - (optional) is a type of number
  standby_maintenance_buffer_in_days = null
  # vault_id - (optional) is a type of string
  vault_id = null

  backup_config = [{
    backup_destination_details = [{
      id             = null
      internet_proxy = null
      type           = null
      vpc_password   = null
      vpc_user       = null
    }]
    recovery_window_in_days = null
  }]

  maintenance_window_details = [{
    days_of_week = [{
      name = null
    }]
    hours_of_day       = []
    lead_time_in_weeks = null
    months = [{
      name = null
    }]
    preference     = null
    weeks_of_month = []
  }]

  peer_autonomous_container_database_backup_config = [{
    backup_destination_details = [{
      id             = null
      internet_proxy = null
      type           = null
      vpc_password   = null
      vpc_user       = null
    }]
    recovery_window_in_days = null
  }]

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
variable "autonomous_exadata_infrastructure_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autonomous_vm_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_unique_name" {
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
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "key_store_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "patch_model" {
  description = "(required)"
  type        = string
}

variable "peer_autonomous_container_database_compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_autonomous_container_database_display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_autonomous_exadata_infrastructure_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_autonomous_vm_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_db_unique_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rotate_key_trigger" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "service_level_agreement_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "standby_maintenance_buffer_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vault_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      backup_destination_details = list(object(
        {
          id             = string
          internet_proxy = string
          type           = string
          vpc_password   = string
          vpc_user       = string
        }
      ))
      recovery_window_in_days = number
    }
  ))
  default = []
}

variable "maintenance_window_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      days_of_week = list(object(
        {
          name = string
        }
      ))
      hours_of_day       = list(number)
      lead_time_in_weeks = number
      months = list(object(
        {
          name = string
        }
      ))
      preference     = string
      weeks_of_month = list(number)
    }
  ))
  default = []
}

variable "peer_autonomous_container_database_backup_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      backup_destination_details = list(object(
        {
          id             = string
          internet_proxy = string
          type           = string
          vpc_password   = string
          vpc_user       = string
        }
      ))
      recovery_window_in_days = number
    }
  ))
  default = []
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
resource "oci_database_autonomous_container_database" "this" {
  # autonomous_exadata_infrastructure_id - (optional) is a type of string
  autonomous_exadata_infrastructure_id = var.autonomous_exadata_infrastructure_id
  # autonomous_vm_cluster_id - (optional) is a type of string
  autonomous_vm_cluster_id = var.autonomous_vm_cluster_id
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # db_unique_name - (optional) is a type of string
  db_unique_name = var.db_unique_name
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (required) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # key_store_id - (optional) is a type of string
  key_store_id = var.key_store_id
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # patch_model - (required) is a type of string
  patch_model = var.patch_model
  # peer_autonomous_container_database_compartment_id - (optional) is a type of string
  peer_autonomous_container_database_compartment_id = var.peer_autonomous_container_database_compartment_id
  # peer_autonomous_container_database_display_name - (optional) is a type of string
  peer_autonomous_container_database_display_name = var.peer_autonomous_container_database_display_name
  # peer_autonomous_exadata_infrastructure_id - (optional) is a type of string
  peer_autonomous_exadata_infrastructure_id = var.peer_autonomous_exadata_infrastructure_id
  # peer_autonomous_vm_cluster_id - (optional) is a type of string
  peer_autonomous_vm_cluster_id = var.peer_autonomous_vm_cluster_id
  # peer_db_unique_name - (optional) is a type of string
  peer_db_unique_name = var.peer_db_unique_name
  # protection_mode - (optional) is a type of string
  protection_mode = var.protection_mode
  # rotate_key_trigger - (optional) is a type of bool
  rotate_key_trigger = var.rotate_key_trigger
  # service_level_agreement_type - (optional) is a type of string
  service_level_agreement_type = var.service_level_agreement_type
  # standby_maintenance_buffer_in_days - (optional) is a type of number
  standby_maintenance_buffer_in_days = var.standby_maintenance_buffer_in_days
  # vault_id - (optional) is a type of string
  vault_id = var.vault_id

  dynamic "backup_config" {
    for_each = var.backup_config
    content {
      # recovery_window_in_days - (optional) is a type of number
      recovery_window_in_days = backup_config.value["recovery_window_in_days"]

      dynamic "backup_destination_details" {
        for_each = backup_config.value.backup_destination_details
        content {
          # id - (optional) is a type of string
          id = backup_destination_details.value["id"]
          # internet_proxy - (optional) is a type of string
          internet_proxy = backup_destination_details.value["internet_proxy"]
          # type - (required) is a type of string
          type = backup_destination_details.value["type"]
          # vpc_password - (optional) is a type of string
          vpc_password = backup_destination_details.value["vpc_password"]
          # vpc_user - (optional) is a type of string
          vpc_user = backup_destination_details.value["vpc_user"]
        }
      }

    }
  }

  dynamic "maintenance_window_details" {
    for_each = var.maintenance_window_details
    content {
      # hours_of_day - (optional) is a type of list of number
      hours_of_day = maintenance_window_details.value["hours_of_day"]
      # lead_time_in_weeks - (optional) is a type of number
      lead_time_in_weeks = maintenance_window_details.value["lead_time_in_weeks"]
      # preference - (required) is a type of string
      preference = maintenance_window_details.value["preference"]
      # weeks_of_month - (optional) is a type of list of number
      weeks_of_month = maintenance_window_details.value["weeks_of_month"]

      dynamic "days_of_week" {
        for_each = maintenance_window_details.value.days_of_week
        content {
          # name - (required) is a type of string
          name = days_of_week.value["name"]
        }
      }

      dynamic "months" {
        for_each = maintenance_window_details.value.months
        content {
          # name - (required) is a type of string
          name = months.value["name"]
        }
      }

    }
  }

  dynamic "peer_autonomous_container_database_backup_config" {
    for_each = var.peer_autonomous_container_database_backup_config
    content {
      # recovery_window_in_days - (optional) is a type of number
      recovery_window_in_days = peer_autonomous_container_database_backup_config.value["recovery_window_in_days"]

      dynamic "backup_destination_details" {
        for_each = peer_autonomous_container_database_backup_config.value.backup_destination_details
        content {
          # id - (optional) is a type of string
          id = backup_destination_details.value["id"]
          # internet_proxy - (optional) is a type of string
          internet_proxy = backup_destination_details.value["internet_proxy"]
          # type - (required) is a type of string
          type = backup_destination_details.value["type"]
          # vpc_password - (optional) is a type of string
          vpc_password = backup_destination_details.value["vpc_password"]
          # vpc_user - (optional) is a type of string
          vpc_user = backup_destination_details.value["vpc_user"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "autonomous_exadata_infrastructure_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.autonomous_exadata_infrastructure_id
}

output "autonomous_vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.autonomous_vm_cluster_id
}

output "availability_domain" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.compartment_id
}

output "db_unique_name" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.db_unique_name
}

output "db_version" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.db_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_container_database.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_container_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.id
}

output "infrastructure_type" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.infrastructure_type
}

output "key_store_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.key_store_id
}

output "key_store_wallet_name" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.key_store_wallet_name
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.kms_key_id
}

output "last_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.last_maintenance_run_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.lifecycle_details
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = oci_database_autonomous_container_database.this.maintenance_window
}

output "next_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.next_maintenance_run_id
}

output "patch_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.patch_id
}

output "peer_autonomous_container_database_compartment_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.peer_autonomous_container_database_compartment_id
}

output "peer_autonomous_container_database_display_name" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.peer_autonomous_container_database_display_name
}

output "peer_autonomous_exadata_infrastructure_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.peer_autonomous_exadata_infrastructure_id
}

output "peer_autonomous_vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.peer_autonomous_vm_cluster_id
}

output "peer_db_unique_name" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.peer_db_unique_name
}

output "protection_mode" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.protection_mode
}

output "role" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.role
}

output "service_level_agreement_type" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.service_level_agreement_type
}

output "standby_maintenance_buffer_in_days" {
  description = "returns a number"
  value       = oci_database_autonomous_container_database.this.standby_maintenance_buffer_in_days
}

output "state" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.time_created
}

output "vault_id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database.this.vault_id
}

output "this" {
  value = oci_database_autonomous_container_database.this
}
```

[top](#index)