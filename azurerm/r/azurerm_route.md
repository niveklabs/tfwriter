# azurerm_route

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
module "azurerm_route" {
  source = "./modules/azurerm/r/azurerm_route"

  # address_prefix - (required) is a type of string
  address_prefix = null
  # name - (required) is a type of string
  name = null
  # next_hop_in_ip_address - (optional) is a type of string
  next_hop_in_ip_address = null
  # next_hop_type - (required) is a type of string
  next_hop_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # route_table_name - (required) is a type of string
  route_table_name = null

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
variable "address_prefix" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "next_hop_in_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "next_hop_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "route_table_name" {
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
resource "azurerm_route" "this" {
  address_prefix         = var.address_prefix
  name                   = var.name
  next_hop_in_ip_address = var.next_hop_in_ip_address
  next_hop_type          = var.next_hop_type
  resource_group_name    = var.resource_group_name
  route_table_name       = var.route_table_name

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
  value       = azurerm_route.this.id
}

output "this" {
  value = azurerm_route.this
}
```

[top](#index)