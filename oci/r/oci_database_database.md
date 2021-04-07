# oci_database_database

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
module "oci_database_database" {
  source = null

  # db_home_id - (required) is a type of string
  db_home_id = null
  # db_version - (optional) is a type of string
  db_version = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # kms_key_migration - (optional) is a type of bool
  kms_key_migration = null
  # kms_key_rotation - (optional) is a type of number
  kms_key_rotation = null
  # kms_key_version_id - (optional) is a type of string
  kms_key_version_id = null
  # source - (required) is a type of string

  database = [{
    admin_password             = null
    backup_id                  = null
    backup_tde_password        = null
    character_set              = null
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
    db_name             = null
    db_unique_name      = null
    db_workload         = null
    defined_tags        = {}
    freeform_tags       = {}
    ncharacter_set      = null
    pdb_name            = null
    tde_wallet_password = null
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
variable "db_home_id" {
  description = "(required)"
  type        = string
}

variable "db_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_migration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key_rotation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kms_key_version_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(required)"
  type        = string
}

variable "database" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      admin_password             = string
      backup_id                  = string
      backup_tde_password        = string
      character_set              = string
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
      db_name             = string
      db_unique_name      = string
      db_workload         = string
      defined_tags        = map(string)
      freeform_tags       = map(string)
      ncharacter_set      = string
      pdb_name            = string
      tde_wallet_password = string
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
resource "oci_database_database" "this" {
  # db_home_id - (required) is a type of string
  db_home_id = var.db_home_id
  # db_version - (optional) is a type of string
  db_version = var.db_version
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # kms_key_migration - (optional) is a type of bool
  kms_key_migration = var.kms_key_migration
  # kms_key_rotation - (optional) is a type of number
  kms_key_rotation = var.kms_key_rotation
  # kms_key_version_id - (optional) is a type of string
  kms_key_version_id = var.kms_key_version_id
  # source - (required) is a type of string
  source = var.source

  dynamic "database" {
    for_each = var.database
    content {
      # admin_password - (required) is a type of string
      admin_password = database.value["admin_password"]
      # backup_id - (optional) is a type of string
      backup_id = database.value["backup_id"]
      # backup_tde_password - (optional) is a type of string
      backup_tde_password = database.value["backup_tde_password"]
      # character_set - (optional) is a type of string
      character_set = database.value["character_set"]
      # database_software_image_id - (optional) is a type of string
      database_software_image_id = database.value["database_software_image_id"]
      # db_name - (required) is a type of string
      db_name = database.value["db_name"]
      # db_unique_name - (optional) is a type of string
      db_unique_name = database.value["db_unique_name"]
      # db_workload - (optional) is a type of string
      db_workload = database.value["db_workload"]
      # defined_tags - (optional) is a type of map of string
      defined_tags = database.value["defined_tags"]
      # freeform_tags - (optional) is a type of map of string
      freeform_tags = database.value["freeform_tags"]
      # ncharacter_set - (optional) is a type of string
      ncharacter_set = database.value["ncharacter_set"]
      # pdb_name - (optional) is a type of string
      pdb_name = database.value["pdb_name"]
      # tde_wallet_password - (optional) is a type of string
      tde_wallet_password = database.value["tde_wallet_password"]

      dynamic "db_backup_config" {
        for_each = database.value.db_backup_config
        content {
          # auto_backup_enabled - (optional) is a type of bool
          auto_backup_enabled = db_backup_config.value["auto_backup_enabled"]
          # auto_backup_window - (optional) is a type of string
          auto_backup_window = db_backup_config.value["auto_backup_window"]
          # recovery_window_in_days - (optional) is a type of number
          recovery_window_in_days = db_backup_config.value["recovery_window_in_days"]

          dynamic "backup_destination_details" {
            for_each = db_backup_config.value.backup_destination_details
            content {
              # id - (optional) is a type of string
              id = backup_destination_details.value["id"]
              # type - (optional) is a type of string
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
output "character_set" {
  description = "returns a string"
  value       = oci_database_database.this.character_set
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_database_database.this.compartment_id
}

output "connection_strings" {
  description = "returns a list of object"
  value       = oci_database_database.this.connection_strings
}

output "database_software_image_id" {
  description = "returns a string"
  value       = oci_database_database.this.database_software_image_id
}

output "db_backup_config" {
  description = "returns a list of object"
  value       = oci_database_database.this.db_backup_config
}

output "db_name" {
  description = "returns a string"
  value       = oci_database_database.this.db_name
}

output "db_system_id" {
  description = "returns a string"
  value       = oci_database_database.this.db_system_id
}

output "db_unique_name" {
  description = "returns a string"
  value       = oci_database_database.this.db_unique_name
}

output "db_version" {
  description = "returns a string"
  value       = oci_database_database.this.db_version
}

output "db_workload" {
  description = "returns a string"
  value       = oci_database_database.this.db_workload
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_database.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_database.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_database_database.this.kms_key_id
}

output "kms_key_version_id" {
  description = "returns a string"
  value       = oci_database_database.this.kms_key_version_id
}

output "last_backup_timestamp" {
  description = "returns a string"
  value       = oci_database_database.this.last_backup_timestamp
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_database.this.lifecycle_details
}

output "ncharacter_set" {
  description = "returns a string"
  value       = oci_database_database.this.ncharacter_set
}

output "pdb_name" {
  description = "returns a string"
  value       = oci_database_database.this.pdb_name
}

output "source_database_point_in_time_recovery_timestamp" {
  description = "returns a string"
  value       = oci_database_database.this.source_database_point_in_time_recovery_timestamp
}

output "state" {
  description = "returns a string"
  value       = oci_database_database.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_database.this.time_created
}

output "vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_database.this.vm_cluster_id
}

output "this" {
  value = oci_database_database.this
}
```

[top](#index)