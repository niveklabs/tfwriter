# oci_database_database_upgrade

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
module "oci_database_database_upgrade" {
  source = "./modules/oci/r/oci_database_database_upgrade"

  # action - (required) is a type of string
  action = null
  # database_id - (required) is a type of string
  database_id = null

  database_upgrade_source_details = [{
    database_software_image_id = null
    db_version                 = null
    options                    = null
    source                     = null
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
variable "action" {
  description = "(required)"
  type        = string
}

variable "database_id" {
  description = "(required)"
  type        = string
}

variable "database_upgrade_source_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      database_software_image_id = string
      db_version                 = string
      options                    = string
      source                     = string
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
resource "oci_database_database_upgrade" "this" {
  # action - (required) is a type of string
  action = var.action
  # database_id - (required) is a type of string
  database_id = var.database_id

  dynamic "database_upgrade_source_details" {
    for_each = var.database_upgrade_source_details
    content {
      # database_software_image_id - (optional) is a type of string
      database_software_image_id = database_upgrade_source_details.value["database_software_image_id"]
      # db_version - (optional) is a type of string
      db_version = database_upgrade_source_details.value["db_version"]
      # options - (optional) is a type of string
      options = database_upgrade_source_details.value["options"]
      # source - (optional) is a type of string
      source = database_upgrade_source_details.value["source"]
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
  value       = oci_database_database_upgrade.this.character_set
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.compartment_id
}

output "connection_strings" {
  description = "returns a list of object"
  value       = oci_database_database_upgrade.this.connection_strings
}

output "database_software_image_id" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.database_software_image_id
}

output "db_backup_config" {
  description = "returns a list of object"
  value       = oci_database_database_upgrade.this.db_backup_config
}

output "db_home_id" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.db_home_id
}

output "db_name" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.db_name
}

output "db_system_id" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.db_system_id
}

output "db_unique_name" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.db_unique_name
}

output "db_workload" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.db_workload
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_database_upgrade.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_database_upgrade.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.id
}

output "last_backup_timestamp" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.last_backup_timestamp
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.lifecycle_details
}

output "ncharacter_set" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.ncharacter_set
}

output "pdb_name" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.pdb_name
}

output "source_database_point_in_time_recovery_timestamp" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.source_database_point_in_time_recovery_timestamp
}

output "state" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.time_created
}

output "vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_database_upgrade.this.vm_cluster_id
}

output "this" {
  value = oci_database_database_upgrade.this
}
```

[top](#index)