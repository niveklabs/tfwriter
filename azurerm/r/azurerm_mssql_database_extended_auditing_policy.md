# azurerm_mssql_database_extended_auditing_policy

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_mssql_database_extended_auditing_policy" {
  source = "./modules/azurerm/r/azurerm_mssql_database_extended_auditing_policy"

  # database_id - (required) is a type of string
  database_id = null
  # log_monitoring_enabled - (optional) is a type of bool
  log_monitoring_enabled = null
  # retention_in_days - (optional) is a type of number
  retention_in_days = null
  # storage_account_access_key - (optional) is a type of string
  storage_account_access_key = null
  # storage_account_access_key_is_secondary - (optional) is a type of bool
  storage_account_access_key_is_secondary = null
  # storage_endpoint - (optional) is a type of string
  storage_endpoint = null

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
variable "database_id" {
  description = "(required)"
  type        = string
}

variable "log_monitoring_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "retention_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "storage_account_access_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_access_key_is_secondary" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "storage_endpoint" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_mssql_database_extended_auditing_policy" "this" {
  # database_id - (required) is a type of string
  database_id = var.database_id
  # log_monitoring_enabled - (optional) is a type of bool
  log_monitoring_enabled = var.log_monitoring_enabled
  # retention_in_days - (optional) is a type of number
  retention_in_days = var.retention_in_days
  # storage_account_access_key - (optional) is a type of string
  storage_account_access_key = var.storage_account_access_key
  # storage_account_access_key_is_secondary - (optional) is a type of bool
  storage_account_access_key_is_secondary = var.storage_account_access_key_is_secondary
  # storage_endpoint - (optional) is a type of string
  storage_endpoint = var.storage_endpoint

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = azurerm_mssql_database_extended_auditing_policy.this.id
}

output "this" {
  value = azurerm_mssql_database_extended_auditing_policy.this
}
```

[top](#index)