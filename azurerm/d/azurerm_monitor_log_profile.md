# azurerm_monitor_log_profile

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/azurerm/d/azurerm_monitor_log_profile"

  # name - (required) is a type of string
  name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_monitor_log_profile" "this" {
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "categories" {
  description = "returns a list of string"
  value       = data.azurerm_monitor_log_profile.this.categories
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_monitor_log_profile.this.id
}

output "locations" {
  description = "returns a list of string"
  value       = data.azurerm_monitor_log_profile.this.locations
}

output "retention_policy" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_log_profile.this.retention_policy
}

output "servicebus_rule_id" {
  description = "returns a string"
  value       = data.azurerm_monitor_log_profile.this.servicebus_rule_id
}

output "storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_monitor_log_profile.this.storage_account_id
}

output "this" {
  value = azurerm_monitor_log_profile.this
}
```

[top](#index)