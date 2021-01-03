# azurerm_mssql_server_security_alert_policy

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_mssql_server_security_alert_policy" {
  source = "./modules/azurerm/r/azurerm_mssql_server_security_alert_policy"

  # disabled_alerts - (optional) is a type of set of string
  disabled_alerts = []
  # email_account_admins - (optional) is a type of bool
  email_account_admins = null
  # email_addresses - (optional) is a type of set of string
  email_addresses = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # retention_days - (optional) is a type of number
  retention_days = null
  # server_name - (required) is a type of string
  server_name = null
  # state - (required) is a type of string
  state = null
  # storage_account_access_key - (optional) is a type of string
  storage_account_access_key = null
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
variable "disabled_alerts" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "email_account_admins" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "email_addresses" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_name" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(required)"
  type        = string
}

variable "storage_account_access_key" {
  description = "(optional)"
  type        = string
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
resource "azurerm_mssql_server_security_alert_policy" "this" {
  disabled_alerts            = var.disabled_alerts
  email_account_admins       = var.email_account_admins
  email_addresses            = var.email_addresses
  resource_group_name        = var.resource_group_name
  retention_days             = var.retention_days
  server_name                = var.server_name
  state                      = var.state
  storage_account_access_key = var.storage_account_access_key
  storage_endpoint           = var.storage_endpoint

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
  value       = azurerm_mssql_server_security_alert_policy.this.id
}

output "this" {
  value = azurerm_mssql_server_security_alert_policy.this
}
```

[top](#index)