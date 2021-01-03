# azurerm_monitor_scheduled_query_rules_log

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_monitor_scheduled_query_rules_log" {
  source = "./modules/azurerm/d/azurerm_monitor_scheduled_query_rules_log"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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

variable "resource_group_name" {
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
data "azurerm_monitor_scheduled_query_rules_log" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "authorized_resource_ids" {
  description = "returns a set of string"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.authorized_resource_ids
}

output "criteria" {
  description = "returns a set of object"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.criteria
}

output "data_source_id" {
  description = "returns a string"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.data_source_id
}

output "description" {
  description = "returns a string"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.location
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_monitor_scheduled_query_rules_log.this.tags
}

output "this" {
  value = azurerm_monitor_scheduled_query_rules_log.this
}
```

[top](#index)