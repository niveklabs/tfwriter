# azurerm_notification_hub_authorization_rule

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
module "azurerm_notification_hub_authorization_rule" {
  source = "./modules/azurerm/r/azurerm_notification_hub_authorization_rule"

  # listen - (optional) is a type of bool
  listen = null
  # manage - (optional) is a type of bool
  manage = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # notification_hub_name - (required) is a type of string
  notification_hub_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # send - (optional) is a type of bool
  send = null

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

variable "notification_hub_name" {
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
resource "azurerm_notification_hub_authorization_rule" "this" {
  listen                = var.listen
  manage                = var.manage
  name                  = var.name
  namespace_name        = var.namespace_name
  notification_hub_name = var.notification_hub_name
  resource_group_name   = var.resource_group_name
  send                  = var.send

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
output "id" {
  description = "returns a string"
  value       = azurerm_notification_hub_authorization_rule.this.id
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurerm_notification_hub_authorization_rule.this.primary_access_key
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurerm_notification_hub_authorization_rule.this.secondary_access_key
}

output "this" {
  value = azurerm_notification_hub_authorization_rule.this
}
```

[top](#index)