# azurerm_service_fabric_mesh_local_network

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
module "azurerm_service_fabric_mesh_local_network" {
  source = "./modules/azurerm/r/azurerm_service_fabric_mesh_local_network"

  # description - (optional) is a type of string
  description = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # network_address_prefix - (required) is a type of string
  network_address_prefix = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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
variable "description" {
  description = "(optional)"
  type        = string
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

variable "network_address_prefix" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
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
resource "azurerm_service_fabric_mesh_local_network" "this" {
  description            = var.description
  location               = var.location
  name                   = var.name
  network_address_prefix = var.network_address_prefix
  resource_group_name    = var.resource_group_name
  tags                   = var.tags

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
  value       = azurerm_service_fabric_mesh_local_network.this.id
}

output "this" {
  value = azurerm_service_fabric_mesh_local_network.this
}
```

[top](#index)