# azurerm_route_table

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
module "azurerm_route_table" {
  source = "./modules/azurerm/r/azurerm_route_table"

  # disable_bgp_route_propagation - (optional) is a type of bool
  disable_bgp_route_propagation = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # route - (optional) is a type of list of object
  route = [{
    address_prefix         = null
    name                   = null
    next_hop_in_ip_address = null
    next_hop_type          = null
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
variable "disable_bgp_route_propagation" {
  description = "(optional)"
  type        = bool
  default     = null
}

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

variable "route" {
  description = "(optional)"
  type = list(object(
    {
      address_prefix         = string
      name                   = string
      next_hop_in_ip_address = string
      next_hop_type          = string
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
resource "azurerm_route_table" "this" {
  disable_bgp_route_propagation = var.disable_bgp_route_propagation
  location                      = var.location
  name                          = var.name
  resource_group_name           = var.resource_group_name
  route                         = var.route
  tags                          = var.tags

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
  value       = azurerm_route_table.this.id
}

output "route" {
  description = "returns a list of object"
  value       = azurerm_route_table.this.route
}

output "subnets" {
  description = "returns a set of string"
  value       = azurerm_route_table.this.subnets
}

output "this" {
  value = azurerm_route_table.this
}
```

[top](#index)