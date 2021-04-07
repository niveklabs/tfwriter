# oci_database_db_home

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
module "oci_database_db_home" {
  source = null

  # database_software_image_id - (optional) is a type of string
  database_software_image_id = null
  # db_system_id - (optional) is a type of string
  db_system_id = null
  # db_version - (optional) is a type of string
  db_version = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # kms_key_version_id - (optional) is a type of string
  kms_key_version_id = null
  # source - (optional) is a type of string
  # vm_cluster_id - (optional) is a type of string
  vm_cluster_id = null

  database = [{
    admin_password      = null
    backup_id           = null
    backup_tde_password = null
    character_set       = null
    connection_strings = [{
      all_connection_strings = {}
      cdb_default            = null
      cdb_ip_default         = null
    }]
    database_id                = null
    database_software_image_id = null
    db_backup_config = [{
      auto_backup_enabled = null
      auto_backup_window  = null
      backup_destination_details = [{
        id   = null
        type = null
      }]
      recovery_window_in_days = null
    }]
    db_name                               = null
    db_unique_name                        = null
    db_workload                           = null
    defined_tags                          = {}
    freeform_tags                         = {}
    id                                    = null
    lifecycle_details                     = null
    ncharacter_set                        = null
    one_off_patches                       = []
    pdb_name                              = null
    state                                 = null
    tde_wallet_password                   = null
    time_created                          = null
    time_stamp_for_point_in_time_recovery = null
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
variable "database_software_image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_version" {
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

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_version_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vm_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      admin_password      = string
      backup_id           = string
      backup_tde_password = string
      character_set       = string
      connection_strings = list(object(
        {
          all_connection_strings = map(string)
          cdb_default            = string
          cdb_ip_default         = string
        }
      ))
      database_id                = string
      database_software_image_id = string
      db_backup_config = list(object(
        {
          auto_backup_enabled = bool
          auto_backup_window  = string
          backup_destination_details = list(object(
            {
              id   = string
              type = string
            }
          ))
          recovery_window_in_days = number
        }
      ))
      db_name                               = string
      db_unique_name                        = string
      db_workload                           = string
      defined_tags                          = map(string)
      freeform_tags                         = map(string)
      id                                    = string
      lifecycle_details                     = string
      ncharacter_set                        = string
      one_off_patches                       = list(string)
      pdb_name                              = string
      state                                 = string
      tde_wallet_password                   = string
      time_created                          = string
      time_stamp_for_point_in_time_recovery = string
    }
  ))
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
resource "oci_database_db_home" "this" {
  database_software_image_id = var.database_software_image_id
  db_system_id               = var.db_system_id
  db_version                 = var.db_version
  defined_tags               = var.defined_tags
  display_name               = var.display_name
  freeform_tags              = var.freeform_tags
  kms_key_id                 = var.kms_key_id
  kms_key_version_id         = var.kms_key_version_id
  source                     = var.source
  vm_cluster_id              = var.vm_cluster_id

  dynamic "database" {
    for_each = var.database
    content {
      admin_password                        = database.value["admin_password"]
      backup_id                             = database.value["backup_id"]
      backup_tde_password                   = database.value["backup_tde_password"]
      character_set                         = database.value["character_set"]
      database_id                           = database.value["database_id"]
      database_software_image_id            = database.value["database_software_image_id"]
      db_name                               = database.value["db_name"]
      db_workload                           = database.value["db_workload"]
      defined_tags                          = database.value["defined_tags"]
      freeform_tags                         = database.value["freeform_tags"]
      ncharacter_set                        = database.value["ncharacter_set"]
      pdb_name                              = database.value["pdb_name"]
      tde_wallet_password                   = database.value["tde_wallet_password"]
      time_stamp_for_point_in_time_recovery = database.value["time_stamp_for_point_in_time_recovery"]

      dynamic "db_backup_config" {
        for_each = database.value.db_backup_config
        content {
          auto_backup_enabled     = db_backup_config.value["auto_backup_enabled"]
          auto_backup_window      = db_backup_config.value["auto_backup_window"]
          recovery_window_in_days = db_backup_config.value["recovery_window_in_days"]

          dynamic "backup_destination_details" {
            for_each = db_backup_config.value.backup_destination_details
            content {
              id   = backup_destination_details.value["id"]
              type = backup_destination_details.value["type"]
            }
          }

        }
      }

    }
  }

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_database_db_home.this.compartment_id
}

output "database_software_image_id" {
  description = "returns a string"
  value       = oci_database_db_home.this.database_software_image_id
}

output "db_home_location" {
  description = "returns a string"
  value       = oci_database_db_home.this.db_home_location
}

output "db_system_id" {
  description = "returns a string"
  value       = oci_database_db_home.this.db_system_id
}

output "db_version" {
  description = "returns a string"
  value       = oci_database_db_home.this.db_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_db_home.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_database_db_home.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_db_home.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_db_home.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_database_db_home.this.kms_key_id
}

output "kms_key_version_id" {
  description = "returns a string"
  value       = oci_database_db_home.this.kms_key_version_id
}

output "last_patch_history_entry_id" {
  description = "returns a string"
  value       = oci_database_db_home.this.last_patch_history_entry_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_db_home.this.lifecycle_details
}

output "source" {
  description = "returns a string"
  value       = oci_database_db_home.this.source
}

output "state" {
  description = "returns a string"
  value       = oci_database_db_home.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_db_home.this.time_created
}

output "vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_db_home.this.vm_cluster_id
}

output "this" {
  value = oci_database_db_home.this
}
```

[top](#index)