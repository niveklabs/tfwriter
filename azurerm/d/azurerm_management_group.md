# azurerm_management_group

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
module "azurerm_management_group" {
  source = "./modules/azurerm/d/azurerm_management_group"

  # display_name - (optional) is a type of string
  display_name = null
  # group_id - (optional) is a type of string
  group_id = null
  # name - (optional) is a type of string
  name = null

  timeouts = [{
    read = null
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
data "azurerm_management_group" "this" {
  display_name = var.display_name
  group_id     = var.group_id
  name         = var.name

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
output "display_name" {
  description = "returns a string"
  value       = data.azurerm_management_group.this.display_name
}

output "group_id" {
  description = "returns a string"
  value       = data.azurerm_management_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_management_group.this.id
}

output "name" {
  description = "returns a string"
  value       = data.azurerm_management_group.this.name
}

output "parent_management_group_id" {
  description = "returns a string"
  value       = data.azurerm_management_group.this.parent_management_group_id
}

output "subscription_ids" {
  description = "returns a set of string"
  value       = data.azurerm_management_group.this.subscription_ids
}

output "this" {
  value = azurerm_management_group.this
}
```

[top](#index)