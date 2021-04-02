# azurerm_servicebus_topic

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
module "azurerm_servicebus_topic" {
  source = "./modules/azurerm/d/azurerm_servicebus_topic"

  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
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

variable "namespace_name" {
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
data "azurerm_servicebus_topic" "this" {
  name                = var.name
  namespace_name      = var.namespace_name
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
output "auto_delete_on_idle" {
  description = "returns a string"
  value       = data.azurerm_servicebus_topic.this.auto_delete_on_idle
}

output "default_message_ttl" {
  description = "returns a string"
  value       = data.azurerm_servicebus_topic.this.default_message_ttl
}

output "duplicate_detection_history_time_window" {
  description = "returns a string"
  value       = data.azurerm_servicebus_topic.this.duplicate_detection_history_time_window
}

output "enable_batched_operations" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_topic.this.enable_batched_operations
}

output "enable_express" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_topic.this.enable_express
}

output "enable_partitioning" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_topic.this.enable_partitioning
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_servicebus_topic.this.id
}

output "max_size_in_megabytes" {
  description = "returns a number"
  value       = data.azurerm_servicebus_topic.this.max_size_in_megabytes
}

output "requires_duplicate_detection" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_topic.this.requires_duplicate_detection
}

output "status" {
  description = "returns a string"
  value       = data.azurerm_servicebus_topic.this.status
}

output "support_ordering" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_topic.this.support_ordering
}

output "this" {
  value = azurerm_servicebus_topic.this
}
```

[top](#index)