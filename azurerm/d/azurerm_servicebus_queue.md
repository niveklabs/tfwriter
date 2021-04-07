# azurerm_servicebus_queue

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
module "azurerm_servicebus_queue" {
  source = "./modules/azurerm/d/azurerm_servicebus_queue"

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
data "azurerm_servicebus_queue" "this" {
  # name - (required) is a type of string
  name = var.name
  # namespace_name - (required) is a type of string
  namespace_name = var.namespace_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
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
  value       = data.azurerm_servicebus_queue.this.auto_delete_on_idle
}

output "dead_lettering_on_message_expiration" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue.this.dead_lettering_on_message_expiration
}

output "default_message_ttl" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue.this.default_message_ttl
}

output "duplicate_detection_history_time_window" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue.this.duplicate_detection_history_time_window
}

output "enable_batched_operations" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue.this.enable_batched_operations
}

output "enable_express" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue.this.enable_express
}

output "enable_partitioning" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue.this.enable_partitioning
}

output "forward_dead_lettered_messages_to" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue.this.forward_dead_lettered_messages_to
}

output "forward_to" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue.this.forward_to
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue.this.id
}

output "lock_duration" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue.this.lock_duration
}

output "max_delivery_count" {
  description = "returns a number"
  value       = data.azurerm_servicebus_queue.this.max_delivery_count
}

output "max_size_in_megabytes" {
  description = "returns a number"
  value       = data.azurerm_servicebus_queue.this.max_size_in_megabytes
}

output "requires_duplicate_detection" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue.this.requires_duplicate_detection
}

output "requires_session" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue.this.requires_session
}

output "status" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue.this.status
}

output "this" {
  value = azurerm_servicebus_queue.this
}
```

[top](#index)