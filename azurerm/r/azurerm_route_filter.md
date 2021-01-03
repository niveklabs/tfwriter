# azurerm_route_filter

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_route_filter" {
  source = "./modules/azurerm/r/azurerm_route_filter"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # rule - (optional) is a type of list of object
  rule = [{
    access      = null
    communities = []
    name        = null
    rule_type   = null
  }]
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "(optional)"
  type = list(object(
    {
      access      = string
      communities = list(string)
      name        = string
      rule_type   = string
    }
  ))
  default = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "azurerm_route_filter" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  rule                = var.rule
  tags                = var.tags

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
  value       = azurerm_route_filter.this.id
}

output "rule" {
  description = "returns a list of object"
  value       = azurerm_route_filter.this.rule
}

output "this" {
  value = azurerm_route_filter.this
}
```

[top](#index)