# azurerm_monitor_log_profile

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
module "azurerm_monitor_log_profile" {
  source = "./modules/azurerm/r/azurerm_monitor_log_profile"

  # categories - (required) is a type of set of string
  categories = []
  # locations - (required) is a type of set of string
  locations = []
  # name - (required) is a type of string
  name = null
  # servicebus_rule_id - (optional) is a type of string
  servicebus_rule_id = null
  # storage_account_id - (optional) is a type of string
  storage_account_id = null

  retention_policy = [{
    days    = null
    enabled = null
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
variable "categories" {
  description = "(required)"
  type        = set(string)
}

variable "locations" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "servicebus_rule_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retention_policy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      days    = number
      enabled = bool
    }
  ))
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
resource "azurerm_monitor_log_profile" "this" {
  # categories - (required) is a type of set of string
  categories = var.categories
  # locations - (required) is a type of set of string
  locations = var.locations
  # name - (required) is a type of string
  name = var.name
  # servicebus_rule_id - (optional) is a type of string
  servicebus_rule_id = var.servicebus_rule_id
  # storage_account_id - (optional) is a type of string
  storage_account_id = var.storage_account_id

  dynamic "retention_policy" {
    for_each = var.retention_policy
    content {
      # days - (optional) is a type of number
      days = retention_policy.value["days"]
      # enabled - (required) is a type of bool
      enabled = retention_policy.value["enabled"]
    }
  }

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
  value       = azurerm_monitor_log_profile.this.id
}

output "this" {
  value = azurerm_monitor_log_profile.this
}
```

[top](#index)