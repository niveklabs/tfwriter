# azurerm_servicebus_subscription

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
module "azurerm_servicebus_subscription" {
  source = "./modules/azurerm/d/azurerm_servicebus_subscription"

  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # topic_name - (required) is a type of string
  topic_name = null

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

variable "topic_name" {
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
data "azurerm_servicebus_subscription" "this" {
  name                = var.name
  namespace_name      = var.namespace_name
  resource_group_name = var.resource_group_name
  topic_name          = var.topic_name

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
  value       = data.azurerm_servicebus_subscription.this.auto_delete_on_idle
}

output "dead_lettering_on_filter_evaluation_error" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_subscription.this.dead_lettering_on_filter_evaluation_error
}

output "dead_lettering_on_message_expiration" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_subscription.this.dead_lettering_on_message_expiration
}

output "default_message_ttl" {
  description = "returns a string"
  value       = data.azurerm_servicebus_subscription.this.default_message_ttl
}

output "enable_batched_operations" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_subscription.this.enable_batched_operations
}

output "forward_dead_lettered_messages_to" {
  description = "returns a string"
  value       = data.azurerm_servicebus_subscription.this.forward_dead_lettered_messages_to
}

output "forward_to" {
  description = "returns a string"
  value       = data.azurerm_servicebus_subscription.this.forward_to
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_servicebus_subscription.this.id
}

output "lock_duration" {
  description = "returns a string"
  value       = data.azurerm_servicebus_subscription.this.lock_duration
}

output "max_delivery_count" {
  description = "returns a number"
  value       = data.azurerm_servicebus_subscription.this.max_delivery_count
}

output "requires_session" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_subscription.this.requires_session
}

output "this" {
  value = azurerm_servicebus_subscription.this
}
```

[top](#index)