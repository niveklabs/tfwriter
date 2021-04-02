# azurerm_management_group

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
module "azurerm_management_group" {
  source = "./modules/azurerm/r/azurerm_management_group"

  # display_name - (optional) is a type of string
  display_name = null
  # group_id - (optional) is a type of string
  group_id = null
  # name - (optional) is a type of string
  name = null
  # parent_management_group_id - (optional) is a type of string
  parent_management_group_id = null
  # subscription_ids - (optional) is a type of set of string
  subscription_ids = []

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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_management_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_ids" {
  description = "(optional)"
  type        = set(string)
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
resource "azurerm_management_group" "this" {
  display_name               = var.display_name
  group_id                   = var.group_id
  name                       = var.name
  parent_management_group_id = var.parent_management_group_id
  subscription_ids           = var.subscription_ids

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
output "display_name" {
  description = "returns a string"
  value       = azurerm_management_group.this.display_name
}

output "group_id" {
  description = "returns a string"
  value       = azurerm_management_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_management_group.this.id
}

output "name" {
  description = "returns a string"
  value       = azurerm_management_group.this.name
}

output "parent_management_group_id" {
  description = "returns a string"
  value       = azurerm_management_group.this.parent_management_group_id
}

output "subscription_ids" {
  description = "returns a set of string"
  value       = azurerm_management_group.this.subscription_ids
}

output "this" {
  value = azurerm_management_group.this
}
```

[top](#index)