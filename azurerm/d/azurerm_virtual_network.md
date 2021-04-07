# azurerm_virtual_network

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
module "azurerm_virtual_network" {
  source = "./modules/azurerm/d/azurerm_virtual_network"

  # name - (required) is a type of string
  name = null
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
data "azurerm_virtual_network" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "address_space" {
  description = "returns a list of string"
  value       = data.azurerm_virtual_network.this.address_space
}

output "dns_servers" {
  description = "returns a list of string"
  value       = data.azurerm_virtual_network.this.dns_servers
}

output "guid" {
  description = "returns a string"
  value       = data.azurerm_virtual_network.this.guid
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_virtual_network.this.location
}

output "subnets" {
  description = "returns a list of string"
  value       = data.azurerm_virtual_network.this.subnets
}

output "vnet_peerings" {
  description = "returns a map of string"
  value       = data.azurerm_virtual_network.this.vnet_peerings
}

output "this" {
  value = azurerm_virtual_network.this
}
```

[top](#index)