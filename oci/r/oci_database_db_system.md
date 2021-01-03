# oci_database_db_system

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_db_system" {
  source = null

  # availability_domain - (required) is a type of string
  availability_domain = null
  # backup_network_nsg_ids - (optional) is a type of set of string
  backup_network_nsg_ids = []
  # backup_subnet_id - (optional) is a type of string
  backup_subnet_id = null
  # cluster_name - (optional) is a type of string
  cluster_name = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # cpu_core_count - (optional) is a type of number
  cpu_core_count = null
  # data_storage_percentage - (optional) is a type of number
  data_storage_percentage = null
  # data_storage_size_in_gb - (optional) is a type of number
  data_storage_size_in_gb = null
  # database_edition - (optional) is a type of string
  database_edition = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # disk_redundancy - (optional) is a type of string
  disk_redundancy = null
  # display_name - (optional) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
  # fault_domains - (optional) is a type of list of string
  fault_domains = []
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # hostname - (required) is a type of string
  hostname = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # kms_key_version_id - (optional) is a type of string
  kms_key_version_id = null
  # license_model - (optional) is a type of string
  license_model = null
  # node_count - (optional) is a type of number
  node_count = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # private_ip - (optional) is a type of string
  private_ip = null
  # shape - (required) is a type of string
  shape = null
  # source - (optional) is a type of string
  # source_db_system_id - (optional) is a type of string
  source_db_system_id = null
  # sparse_diskgroup - (optional) is a type of bool
  sparse_diskgroup = null
  # ssh_public_keys - (required) is a type of set of string
  ssh_public_keys = []
  # subnet_id - (required) is a type of string
  subnet_id = null
  # time_zone - (optional) is a type of string
  time_zone = null

  db_home = [{
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
      db_domain                             = null
      db_name                               = null
      db_unique_name                        = null
      db_workload                           = null
      defined_tags                          = {}
      freeform_tags                         = {}
      id                                    = null
      lifecycle_details                     = null
      ncharacter_set                        = null
      pdb_name                              = null
      state                                 = null
      tde_wallet_password                   = null
      time_created                          = null
      time_stamp_for_point_in_time_recovery = null
    }]
    database_software_image_id  = null
    db_home_location            = null
    db_version                  = null
    defined_tags                = {}
    display_name                = null
    freeform_tags               = {}
    id                          = null
    last_patch_history_entry_id = null
    lifecycle_details           = null
    state                       = null
    time_created                = null
  }]

  db_system_options = [{
    storage_management = null
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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "backup_network_nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backup_subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "cpu_core_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "data_storage_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "data_storage_size_in_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "database_edition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "disk_redundancy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fault_domains" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "hostname" {
  description = "(required)"
  type        = string
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

variable "license_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_db_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sparse_diskgroup" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssh_public_keys" {
  description = "(required)"
  type        = set(string)
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "time_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_home" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      database = list(object(
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
          db_domain                             = string
          db_name                               = string
          db_unique_name                        = string
          db_workload                           = string
          defined_tags                          = map(string)
          freeform_tags                         = map(string)
          id                                    = string
          lifecycle_details                     = string
          ncharacter_set                        = string
          pdb_name                              = string
          state                                 = string
          tde_wallet_password                   = string
          time_created                          = string
          time_stamp_for_point_in_time_recovery = string
        }
      ))
      database_software_image_id  = string
      db_home_location            = string
      db_version                  = string
      defined_tags                = map(string)
      display_name                = string
      freeform_tags               = map(string)
      id                          = string
      last_patch_history_entry_id = string
      lifecycle_details           = string
      state                       = string
      time_created                = string
    }
  ))
}

variable "db_system_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      storage_management = string
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
resource "oci_database_db_system" "this" {
  availability_domain     = var.availability_domain
  backup_network_nsg_ids  = var.backup_network_nsg_ids
  backup_subnet_id        = var.backup_subnet_id
  cluster_name            = var.cluster_name
  compartment_id          = var.compartment_id
  cpu_core_count          = var.cpu_core_count
  data_storage_percentage = var.data_storage_percentage
  data_storage_size_in_gb = var.data_storage_size_in_gb
  database_edition        = var.database_edition
  defined_tags            = var.defined_tags
  disk_redundancy         = var.disk_redundancy
  display_name            = var.display_name
  domain                  = var.domain
  fault_domains           = var.fault_domains
  freeform_tags           = var.freeform_tags
  hostname                = var.hostname
  kms_key_id              = var.kms_key_id
  kms_key_version_id      = var.kms_key_version_id
  license_model           = var.license_model
  node_count              = var.node_count
  nsg_ids                 = var.nsg_ids
  private_ip              = var.private_ip
  shape                   = var.shape
  source                  = var.source
  source_db_system_id     = var.source_db_system_id
  sparse_diskgroup        = var.sparse_diskgroup
  ssh_public_keys         = var.ssh_public_keys
  subnet_id               = var.subnet_id
  time_zone               = var.time_zone

  dynamic "db_home" {
    for_each = var.db_home
    content {
      database_software_image_id = db_home.value["database_software_image_id"]
      db_version                 = db_home.value["db_version"]
      defined_tags               = db_home.value["defined_tags"]
      display_name               = db_home.value["display_name"]
      freeform_tags              = db_home.value["freeform_tags"]

      dynamic "database" {
        for_each = db_home.value.database
        content {
          admin_password                        = database.value["admin_password"]
          backup_id                             = database.value["backup_id"]
          backup_tde_password                   = database.value["backup_tde_password"]
          character_set                         = database.value["character_set"]
          database_id                           = database.value["database_id"]
          database_software_image_id            = database.value["database_software_image_id"]
          db_domain                             = database.value["db_domain"]
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

    }
  }

  dynamic "db_system_options" {
    for_each = var.db_system_options
    content {
      storage_management = db_system_options.value["storage_management"]
    }
  }

  dynamic "maintenance_window_details" {
    for_each = var.maintenance_window_details
    content {
      hours_of_day       = maintenance_window_details.value["hours_of_day"]
      lead_time_in_weeks = maintenance_window_details.value["lead_time_in_weeks"]
      preference         = maintenance_window_details.value["preference"]
      weeks_of_month     = maintenance_window_details.value["weeks_of_month"]

      dynamic "days_of_week" {
        for_each = maintenance_window_details.value.days_of_week
        content {
          name = days_of_week.value["name"]
        }
      }

      dynamic "months" {
        for_each = maintenance_window_details.value.months
        content {
          name = months.value["name"]
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
output "backup_subnet_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.backup_subnet_id
}

output "cluster_name" {
  description = "returns a string"
  value       = oci_database_db_system.this.cluster_name
}

output "cpu_core_count" {
  description = "returns a number"
  value       = oci_database_db_system.this.cpu_core_count
}

output "data_storage_percentage" {
  description = "returns a number"
  value       = oci_database_db_system.this.data_storage_percentage
}

output "data_storage_size_in_gb" {
  description = "returns a number"
  value       = oci_database_db_system.this.data_storage_size_in_gb
}

output "database_edition" {
  description = "returns a string"
  value       = oci_database_db_system.this.database_edition
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_db_system.this.defined_tags
}

output "disk_redundancy" {
  description = "returns a string"
  value       = oci_database_db_system.this.disk_redundancy
}

output "display_name" {
  description = "returns a string"
  value       = oci_database_db_system.this.display_name
}

output "domain" {
  description = "returns a string"
  value       = oci_database_db_system.this.domain
}

output "fault_domains" {
  description = "returns a list of string"
  value       = oci_database_db_system.this.fault_domains
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_db_system.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_db_system.this.id
}

output "iorm_config_cache" {
  description = "returns a list of object"
  value       = oci_database_db_system.this.iorm_config_cache
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.kms_key_id
}

output "kms_key_version_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.kms_key_version_id
}

output "last_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.last_maintenance_run_id
}

output "last_patch_history_entry_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.last_patch_history_entry_id
}

output "license_model" {
  description = "returns a string"
  value       = oci_database_db_system.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_db_system.this.lifecycle_details
}

output "listener_port" {
  description = "returns a number"
  value       = oci_database_db_system.this.listener_port
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = oci_database_db_system.this.maintenance_window
}

output "next_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.next_maintenance_run_id
}

output "node_count" {
  description = "returns a number"
  value       = oci_database_db_system.this.node_count
}

output "point_in_time_data_disk_clone_timestamp" {
  description = "returns a string"
  value       = oci_database_db_system.this.point_in_time_data_disk_clone_timestamp
}

output "private_ip" {
  description = "returns a string"
  value       = oci_database_db_system.this.private_ip
}

output "reco_storage_size_in_gb" {
  description = "returns a number"
  value       = oci_database_db_system.this.reco_storage_size_in_gb
}

output "scan_dns_record_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.scan_dns_record_id
}

output "scan_ip_ids" {
  description = "returns a list of string"
  value       = oci_database_db_system.this.scan_ip_ids
}

output "source" {
  description = "returns a string"
  value       = oci_database_db_system.this.source
}

output "source_db_system_id" {
  description = "returns a string"
  value       = oci_database_db_system.this.source_db_system_id
}

output "sparse_diskgroup" {
  description = "returns a bool"
  value       = oci_database_db_system.this.sparse_diskgroup
}

output "state" {
  description = "returns a string"
  value       = oci_database_db_system.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_db_system.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = oci_database_db_system.this.time_zone
}

output "version" {
  description = "returns a string"
  value       = oci_database_db_system.this.version
}

output "vip_ids" {
  description = "returns a list of string"
  value       = oci_database_db_system.this.vip_ids
}

output "this" {
  value = oci_database_db_system.this
}
```

[top](#index)