# azurerm_servicebus_queue_authorization_rule

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_servicebus_queue_authorization_rule" {
  source = "./modules/azurerm/d/azurerm_servicebus_queue_authorization_rule"

  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # queue_name - (required) is a type of string
  queue_name = null
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

variable "queue_name" {
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
data "azurerm_servicebus_queue_authorization_rule" "this" {
  name                = var.name
  namespace_name      = var.namespace_name
  queue_name          = var.queue_name
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
output "id" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.id
}

output "listen" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.listen
}

output "manage" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.manage
}

output "primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.primary_connection_string
  sensitive   = true
}

output "primary_key" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.primary_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.secondary_connection_string
  sensitive   = true
}

output "secondary_key" {
  description = "returns a string"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.secondary_key
  sensitive   = true
}

output "send" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_queue_authorization_rule.this.send
}

output "this" {
  value = azurerm_servicebus_queue_authorization_rule.this
}
```

[top](#index)