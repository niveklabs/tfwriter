# azurerm_servicebus_topic

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
module "azurerm_servicebus_topic" {
  source = "./modules/azurerm/r/azurerm_servicebus_topic"

  # auto_delete_on_idle - (optional) is a type of string
  auto_delete_on_idle = null
  # default_message_ttl - (optional) is a type of string
  default_message_ttl = null
  # duplicate_detection_history_time_window - (optional) is a type of string
  duplicate_detection_history_time_window = null
  # enable_batched_operations - (optional) is a type of bool
  enable_batched_operations = null
  # enable_express - (optional) is a type of bool
  enable_express = null
  # enable_partitioning - (optional) is a type of bool
  enable_partitioning = null
  # max_size_in_megabytes - (optional) is a type of number
  max_size_in_megabytes = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # requires_duplicate_detection - (optional) is a type of bool
  requires_duplicate_detection = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # status - (optional) is a type of string
  status = null
  # support_ordering - (optional) is a type of bool
  support_ordering = null

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

variable "default_message_ttl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duplicate_detection_history_time_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_batched_operations" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_express" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_partitioning" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_size_in_megabytes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "requires_duplicate_detection" {
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

variable "support_ordering" {
  description = "(optional)"
  type        = bool
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
resource "azurerm_servicebus_topic" "this" {
  auto_delete_on_idle                     = var.auto_delete_on_idle
  default_message_ttl                     = var.default_message_ttl
  duplicate_detection_history_time_window = var.duplicate_detection_history_time_window
  enable_batched_operations               = var.enable_batched_operations
  enable_express                          = var.enable_express
  enable_partitioning                     = var.enable_partitioning
  max_size_in_megabytes                   = var.max_size_in_megabytes
  name                                    = var.name
  namespace_name                          = var.namespace_name
  requires_duplicate_detection            = var.requires_duplicate_detection
  resource_group_name                     = var.resource_group_name
  status                                  = var.status
  support_ordering                        = var.support_ordering

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
  value       = azurerm_servicebus_topic.this.auto_delete_on_idle
}

output "default_message_ttl" {
  description = "returns a string"
  value       = azurerm_servicebus_topic.this.default_message_ttl
}

output "duplicate_detection_history_time_window" {
  description = "returns a string"
  value       = azurerm_servicebus_topic.this.duplicate_detection_history_time_window
}

output "id" {
  description = "returns a string"
  value       = azurerm_servicebus_topic.this.id
}

output "max_size_in_megabytes" {
  description = "returns a number"
  value       = azurerm_servicebus_topic.this.max_size_in_megabytes
}

output "this" {
  value = azurerm_servicebus_topic.this
}
```

[top](#index)