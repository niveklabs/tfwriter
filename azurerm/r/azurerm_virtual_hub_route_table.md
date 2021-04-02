# azurerm_virtual_hub_route_table

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
module "azurerm_virtual_hub_route_table" {
  source = "./modules/azurerm/r/azurerm_virtual_hub_route_table"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # virtual_hub_id - (required) is a type of string
  virtual_hub_id = null

  route = [{
    destinations      = []
    destinations_type = null
    name              = null
    next_hop          = null
    next_hop_type     = null
  }]

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
variable "labels" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "virtual_hub_id" {
  description = "(required)"
  type        = string
}

variable "route" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      destinations      = set(string)
      destinations_type = string
      name              = string
      next_hop          = string
      next_hop_type     = string
    }
  ))
  default = []
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
resource "azurerm_virtual_hub_route_table" "this" {
  labels         = var.labels
  name           = var.name
  virtual_hub_id = var.virtual_hub_id

  dynamic "route" {
    for_each = var.route
    content {
      destinations      = route.value["destinations"]
      destinations_type = route.value["destinations_type"]
      name              = route.value["name"]
      next_hop          = route.value["next_hop"]
      next_hop_type     = route.value["next_hop_type"]
    }
  }

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
  value       = azurerm_virtual_hub_route_table.this.id
}

output "this" {
  value = azurerm_virtual_hub_route_table.this
}
```

[top](#index)