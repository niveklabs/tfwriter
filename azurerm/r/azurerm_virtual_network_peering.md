# azurerm_virtual_network_peering

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
module "azurerm_virtual_network_peering" {
  source = "./modules/azurerm/r/azurerm_virtual_network_peering"

  # allow_forwarded_traffic - (optional) is a type of bool
  allow_forwarded_traffic = null
  # allow_gateway_transit - (optional) is a type of bool
  allow_gateway_transit = null
  # allow_virtual_network_access - (optional) is a type of bool
  allow_virtual_network_access = null
  # name - (required) is a type of string
  name = null
  # remote_virtual_network_id - (required) is a type of string
  remote_virtual_network_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # use_remote_gateways - (optional) is a type of bool
  use_remote_gateways = null
  # virtual_network_name - (required) is a type of string
  virtual_network_name = null

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
variable "allow_forwarded_traffic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_gateway_transit" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_virtual_network_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "remote_virtual_network_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "use_remote_gateways" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "virtual_network_name" {
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
resource "azurerm_virtual_network_peering" "this" {
  allow_forwarded_traffic      = var.allow_forwarded_traffic
  allow_gateway_transit        = var.allow_gateway_transit
  allow_virtual_network_access = var.allow_virtual_network_access
  name                         = var.name
  remote_virtual_network_id    = var.remote_virtual_network_id
  resource_group_name          = var.resource_group_name
  use_remote_gateways          = var.use_remote_gateways
  virtual_network_name         = var.virtual_network_name

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
output "allow_forwarded_traffic" {
  description = "returns a bool"
  value       = azurerm_virtual_network_peering.this.allow_forwarded_traffic
}

output "allow_gateway_transit" {
  description = "returns a bool"
  value       = azurerm_virtual_network_peering.this.allow_gateway_transit
}

output "id" {
  description = "returns a string"
  value       = azurerm_virtual_network_peering.this.id
}

output "use_remote_gateways" {
  description = "returns a bool"
  value       = azurerm_virtual_network_peering.this.use_remote_gateways
}

output "this" {
  value = azurerm_virtual_network_peering.this
}
```

[top](#index)