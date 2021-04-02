# azurerm_eventhub_authorization_rule

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
module "azurerm_eventhub_authorization_rule" {
  source = "./modules/azurerm/d/azurerm_eventhub_authorization_rule"

  # eventhub_name - (required) is a type of string
  eventhub_name = null
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

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "eventhub_name" {
  description = "(required)"
  type        = string
}

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
data "azurerm_eventhub_authorization_rule" "this" {
  eventhub_name       = var.eventhub_name
  listen              = var.listen
  manage              = var.manage
  name                = var.name
  namespace_name      = var.namespace_name
  resource_group_name = var.resource_group_name
  send                = var.send

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
  value       = data.azurerm_eventhub_authorization_rule.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_eventhub_authorization_rule.this.location
}

output "primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_eventhub_authorization_rule.this.primary_connection_string
  sensitive   = true
}

output "primary_connection_string_alias" {
  description = "returns a string"
  value       = data.azurerm_eventhub_authorization_rule.this.primary_connection_string_alias
  sensitive   = true
}

output "primary_key" {
  description = "returns a string"
  value       = data.azurerm_eventhub_authorization_rule.this.primary_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_eventhub_authorization_rule.this.secondary_connection_string
  sensitive   = true
}

output "secondary_connection_string_alias" {
  description = "returns a string"
  value       = data.azurerm_eventhub_authorization_rule.this.secondary_connection_string_alias
  sensitive   = true
}

output "secondary_key" {
  description = "returns a string"
  value       = data.azurerm_eventhub_authorization_rule.this.secondary_key
  sensitive   = true
}

output "this" {
  value = azurerm_eventhub_authorization_rule.this
}
```

[top](#index)