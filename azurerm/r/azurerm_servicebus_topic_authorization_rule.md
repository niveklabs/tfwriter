# azurerm_servicebus_topic_authorization_rule

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
module "azurerm_servicebus_topic_authorization_rule" {
  source = "./modules/azurerm/r/azurerm_servicebus_topic_authorization_rule"

  # listen - (optional) is a type of bool
  listen = null
  # manage - (optional) is a type of bool
  manage = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # send - (optional) is a type of bool
  send = null
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
variable "listen" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "manage" {
  description = "(optional)"
  type        = bool
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "send" {
  description = "(optional)"
  type        = bool
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
resource "azurerm_servicebus_topic_authorization_rule" "this" {
  # listen - (optional) is a type of bool
  listen = var.listen
  # manage - (optional) is a type of bool
  manage = var.manage
  # name - (required) is a type of string
  name = var.name
  # namespace_name - (required) is a type of string
  namespace_name = var.namespace_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # send - (optional) is a type of bool
  send = var.send
  # topic_name - (required) is a type of string
  topic_name = var.topic_name

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
  value       = azurerm_servicebus_topic_authorization_rule.this.id
}

output "primary_connection_string" {
  description = "returns a string"
  value       = azurerm_servicebus_topic_authorization_rule.this.primary_connection_string
  sensitive   = true
}

output "primary_key" {
  description = "returns a string"
  value       = azurerm_servicebus_topic_authorization_rule.this.primary_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_servicebus_topic_authorization_rule.this.secondary_connection_string
  sensitive   = true
}

output "secondary_key" {
  description = "returns a string"
  value       = azurerm_servicebus_topic_authorization_rule.this.secondary_key
  sensitive   = true
}

output "this" {
  value = azurerm_servicebus_topic_authorization_rule.this
}
```

[top](#index)