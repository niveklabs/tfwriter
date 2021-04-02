# azurerm_virtual_network_gateway

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
module "azurerm_virtual_network_gateway" {
  source = "./modules/azurerm/d/azurerm_virtual_network_gateway"

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
data "azurerm_virtual_network_gateway" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "active_active" {
  description = "returns a bool"
  value       = data.azurerm_virtual_network_gateway.this.active_active
}

output "bgp_settings" {
  description = "returns a list of object"
  value       = data.azurerm_virtual_network_gateway.this.bgp_settings
}

output "custom_route" {
  description = "returns a list of object"
  value       = data.azurerm_virtual_network_gateway.this.custom_route
}

output "default_local_network_gateway_id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway.this.default_local_network_gateway_id
}

output "enable_bgp" {
  description = "returns a bool"
  value       = data.azurerm_virtual_network_gateway.this.enable_bgp
}

output "generation" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway.this.generation
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway.this.id
}

output "ip_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_virtual_network_gateway.this.ip_configuration
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway.this.location
}

output "private_ip_address_enabled" {
  description = "returns a bool"
  value       = data.azurerm_virtual_network_gateway.this.private_ip_address_enabled
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_virtual_network_gateway.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway.this.type
}

output "vpn_client_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_virtual_network_gateway.this.vpn_client_configuration
}

output "vpn_type" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway.this.vpn_type
}

output "this" {
  value = azurerm_virtual_network_gateway.this
}
```

[top](#index)