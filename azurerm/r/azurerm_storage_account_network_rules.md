# azurerm_storage_account_network_rules

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
module "azurerm_storage_account_network_rules" {
  source = "./modules/azurerm/r/azurerm_storage_account_network_rules"

  # bypass - (optional) is a type of set of string
  bypass = []
  # default_action - (required) is a type of string
  default_action = null
  # ip_rules - (optional) is a type of set of string
  ip_rules = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null
  # virtual_network_subnet_ids - (optional) is a type of set of string
  virtual_network_subnet_ids = []

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
variable "bypass" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "default_action" {
  description = "(required)"
  type        = string
}

variable "ip_rules" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_account_name" {
  description = "(required)"
  type        = string
}

variable "virtual_network_subnet_ids" {
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
resource "azurerm_storage_account_network_rules" "this" {
  bypass                     = var.bypass
  default_action             = var.default_action
  ip_rules                   = var.ip_rules
  resource_group_name        = var.resource_group_name
  storage_account_name       = var.storage_account_name
  virtual_network_subnet_ids = var.virtual_network_subnet_ids

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
output "bypass" {
  description = "returns a set of string"
  value       = azurerm_storage_account_network_rules.this.bypass
}

output "id" {
  description = "returns a string"
  value       = azurerm_storage_account_network_rules.this.id
}

output "ip_rules" {
  description = "returns a set of string"
  value       = azurerm_storage_account_network_rules.this.ip_rules
}

output "virtual_network_subnet_ids" {
  description = "returns a set of string"
  value       = azurerm_storage_account_network_rules.this.virtual_network_subnet_ids
}

output "this" {
  value = azurerm_storage_account_network_rules.this
}
```

[top](#index)