# azurerm_mssql_virtual_machine

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_mssql_virtual_machine" {
  source = "./modules/azurerm/r/azurerm_mssql_virtual_machine"

  # r_services_enabled - (optional) is a type of bool
  r_services_enabled = null
  # sql_connectivity_port - (optional) is a type of number
  sql_connectivity_port = null
  # sql_connectivity_type - (optional) is a type of string
  sql_connectivity_type = null
  # sql_connectivity_update_password - (optional) is a type of string
  sql_connectivity_update_password = null
  # sql_connectivity_update_username - (optional) is a type of string
  sql_connectivity_update_username = null
  # sql_license_type - (required) is a type of string
  sql_license_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null

  auto_backup = [{
    encryption_enabled  = null
    encryption_password = null
    manual_schedule = [{
      full_backup_frequency           = null
      full_backup_start_hour          = null
      full_backup_window_in_hours     = null
      log_backup_frequency_in_minutes = null
    }]
    retention_period_in_days        = null
    storage_account_access_key      = null
    storage_blob_endpoint           = null
    system_databases_backup_enabled = null
  }]

  auto_patching = [{
    day_of_week                            = null
    maintenance_window_duration_in_minutes = null
    maintenance_window_starting_hour       = null
  }]

  key_vault_credential = [{
    key_vault_url            = null
    name                     = null
    service_principal_name   = null
    service_principal_secret = null
  }]

  storage_configuration = [{
    data_settings = [{
      default_file_path = null
      luns              = []
    }]
    disk_type = null
    log_settings = [{
      default_file_path = null
      luns              = []
    }]
    storage_workload_type = null
    temp_db_settings = [{
      default_file_path = null
      luns              = []
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "r_services_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sql_connectivity_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sql_connectivity_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sql_connectivity_update_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sql_connectivity_update_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sql_license_type" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_machine_id" {
  description = "(required)"
  type        = string
}

variable "auto_backup" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      encryption_enabled  = bool
      encryption_password = string
      manual_schedule = list(object(
        {
          full_backup_frequency           = string
          full_backup_start_hour          = number
          full_backup_window_in_hours     = number
          log_backup_frequency_in_minutes = number
        }
      ))
      retention_period_in_days        = number
      storage_account_access_key      = string
      storage_blob_endpoint           = string
      system_databases_backup_enabled = bool
    }
  ))
  default = []
}

variable "auto_patching" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      day_of_week                            = string
      maintenance_window_duration_in_minutes = number
      maintenance_window_starting_hour       = number
    }
  ))
  default = []
}

variable "key_vault_credential" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      key_vault_url            = string
      name                     = string
      service_principal_name   = string
      service_principal_secret = string
    }
  ))
  default = []
}

variable "storage_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_settings = list(object(
        {
          default_file_path = string
          luns              = list(number)
        }
      ))
      disk_type = string
      log_settings = list(object(
        {
          default_file_path = string
          luns              = list(number)
        }
      ))
      storage_workload_type = string
      temp_db_settings = list(object(
        {
          default_file_path = string
          luns              = list(number)
        }
      ))
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
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_mssql_virtual_machine" "this" {
  r_services_enabled               = var.r_services_enabled
  sql_connectivity_port            = var.sql_connectivity_port
  sql_connectivity_type            = var.sql_connectivity_type
  sql_connectivity_update_password = var.sql_connectivity_update_password
  sql_connectivity_update_username = var.sql_connectivity_update_username
  sql_license_type                 = var.sql_license_type
  tags                             = var.tags
  virtual_machine_id               = var.virtual_machine_id

  dynamic "auto_backup" {
    for_each = var.auto_backup
    content {
      encryption_enabled              = auto_backup.value["encryption_enabled"]
      encryption_password             = auto_backup.value["encryption_password"]
      retention_period_in_days        = auto_backup.value["retention_period_in_days"]
      storage_account_access_key      = auto_backup.value["storage_account_access_key"]
      storage_blob_endpoint           = auto_backup.value["storage_blob_endpoint"]
      system_databases_backup_enabled = auto_backup.value["system_databases_backup_enabled"]

      dynamic "manual_schedule" {
        for_each = auto_backup.value.manual_schedule
        content {
          full_backup_frequency           = manual_schedule.value["full_backup_frequency"]
          full_backup_start_hour          = manual_schedule.value["full_backup_start_hour"]
          full_backup_window_in_hours     = manual_schedule.value["full_backup_window_in_hours"]
          log_backup_frequency_in_minutes = manual_schedule.value["log_backup_frequency_in_minutes"]
        }
      }

    }
  }

  dynamic "auto_patching" {
    for_each = var.auto_patching
    content {
      day_of_week                            = auto_patching.value["day_of_week"]
      maintenance_window_duration_in_minutes = auto_patching.value["maintenance_window_duration_in_minutes"]
      maintenance_window_starting_hour       = auto_patching.value["maintenance_window_starting_hour"]
    }
  }

  dynamic "key_vault_credential" {
    for_each = var.key_vault_credential
    content {
      key_vault_url            = key_vault_credential.value["key_vault_url"]
      name                     = key_vault_credential.value["name"]
      service_principal_name   = key_vault_credential.value["service_principal_name"]
      service_principal_secret = key_vault_credential.value["service_principal_secret"]
    }
  }

  dynamic "storage_configuration" {
    for_each = var.storage_configuration
    content {
      disk_type             = storage_configuration.value["disk_type"]
      storage_workload_type = storage_configuration.value["storage_workload_type"]

      dynamic "data_settings" {
        for_each = storage_configuration.value.data_settings
        content {
          default_file_path = data_settings.value["default_file_path"]
          luns              = data_settings.value["luns"]
        }
      }

      dynamic "log_settings" {
        for_each = storage_configuration.value.log_settings
        content {
          default_file_path = log_settings.value["default_file_path"]
          luns              = log_settings.value["luns"]
        }
      }

      dynamic "temp_db_settings" {
        for_each = storage_configuration.value.temp_db_settings
        content {
          default_file_path = temp_db_settings.value["default_file_path"]
          luns              = temp_db_settings.value["luns"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_mssql_virtual_machine.this.id
}

output "this" {
  value = azurerm_mssql_virtual_machine.this
}
```

[top](#index)