# azurerm_servicebus_subscription

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
module "azurerm_servicebus_subscription" {
  source = "./modules/azurerm/r/azurerm_servicebus_subscription"

  # auto_delete_on_idle - (optional) is a type of string
  auto_delete_on_idle = null
  # dead_lettering_on_filter_evaluation_error - (optional) is a type of bool
  dead_lettering_on_filter_evaluation_error = null
  # dead_lettering_on_message_expiration - (optional) is a type of bool
  dead_lettering_on_message_expiration = null
  # default_message_ttl - (optional) is a type of string
  default_message_ttl = null
  # enable_batched_operations - (optional) is a type of bool
  enable_batched_operations = null
  # forward_dead_lettered_messages_to - (optional) is a type of string
  forward_dead_lettered_messages_to = null
  # forward_to - (optional) is a type of string
  forward_to = null
  # lock_duration - (optional) is a type of string
  lock_duration = null
  # max_delivery_count - (required) is a type of number
  max_delivery_count = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # requires_session - (optional) is a type of bool
  requires_session = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # status - (optional) is a type of string
  status = null
  # topic_name - (required) is a type of string
  topic_name = null

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
variable "auto_delete_on_idle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dead_lettering_on_filter_evaluation_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dead_lettering_on_message_expiration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "default_message_ttl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_batched_operations" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "forward_dead_lettered_messages_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lock_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_delivery_count" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "requires_session" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "topic_name" {
  description = "(required)"
  type        = string
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
resource "azurerm_servicebus_subscription" "this" {
  auto_delete_on_idle                       = var.auto_delete_on_idle
  dead_lettering_on_filter_evaluation_error = var.dead_lettering_on_filter_evaluation_error
  dead_lettering_on_message_expiration      = var.dead_lettering_on_message_expiration
  default_message_ttl                       = var.default_message_ttl
  enable_batched_operations                 = var.enable_batched_operations
  forward_dead_lettered_messages_to         = var.forward_dead_lettered_messages_to
  forward_to                                = var.forward_to
  lock_duration                             = var.lock_duration
  max_delivery_count                        = var.max_delivery_count
  name                                      = var.name
  namespace_name                            = var.namespace_name
  requires_session                          = var.requires_session
  resource_group_name                       = var.resource_group_name
  status                                    = var.status
  topic_name                                = var.topic_name

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
output "auto_delete_on_idle" {
  description = "returns a string"
  value       = azurerm_servicebus_subscription.this.auto_delete_on_idle
}

output "default_message_ttl" {
  description = "returns a string"
  value       = azurerm_servicebus_subscription.this.default_message_ttl
}

output "id" {
  description = "returns a string"
  value       = azurerm_servicebus_subscription.this.id
}

output "lock_duration" {
  description = "returns a string"
  value       = azurerm_servicebus_subscription.this.lock_duration
}

output "this" {
  value = azurerm_servicebus_subscription.this
}
```

[top](#index)