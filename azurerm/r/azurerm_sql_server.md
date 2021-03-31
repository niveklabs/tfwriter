# azurerm_sql_server

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
module "azurerm_sql_server" {
  source = "./modules/azurerm/r/azurerm_sql_server"

  # administrator_login - (required) is a type of string
  administrator_login = null
  # administrator_login_password - (required) is a type of string
  administrator_login_password = null
  # connection_policy - (optional) is a type of string
  connection_policy = null
  # extended_auditing_policy - (optional) is a type of list of object
  extended_auditing_policy = [{
    log_monitoring_enabled                  = null
    retention_in_days                       = null
    storage_account_access_key              = null
    storage_account_access_key_is_secondary = null
    storage_endpoint                        = null
  }]
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (required) is a type of string
  version = null

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
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
variable "administrator_login" {
  description = "(required)"
  type        = string
}

variable "administrator_login_password" {
  description = "(required)"
  type        = string
}

variable "connection_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_auditing_policy" {
  description = "(optional)"
  type = list(object(
    {
      log_monitoring_enabled                  = bool
      retention_in_days                       = number
      storage_account_access_key              = string
      storage_account_access_key_is_secondary = bool
      storage_endpoint                        = string
    }
  ))
  default = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
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
resource "azurerm_sql_server" "this" {
  administrator_login          = var.administrator_login
  administrator_login_password = var.administrator_login_password
  connection_policy            = var.connection_policy
  extended_auditing_policy     = var.extended_auditing_policy
  location                     = var.location
  name                         = var.name
  resource_group_name          = var.resource_group_name
  tags                         = var.tags
  version                      = var.version

  dynamic "identity" {
    for_each = var.identity
    content {
      type = identity.value["type"]
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
output "extended_auditing_policy" {
  description = "returns a list of object"
  value       = azurerm_sql_server.this.extended_auditing_policy
}

output "fully_qualified_domain_name" {
  description = "returns a string"
  value       = azurerm_sql_server.this.fully_qualified_domain_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_sql_server.this.id
}

output "this" {
  value = azurerm_sql_server.this
}
```

[top](#index)