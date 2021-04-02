# azurerm_virtual_hub_connection

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
module "azurerm_virtual_hub_connection" {
  source = "./modules/azurerm/r/azurerm_virtual_hub_connection"

  # hub_to_vitual_network_traffic_allowed - (optional) is a type of bool
  hub_to_vitual_network_traffic_allowed = null
  # internet_security_enabled - (optional) is a type of bool
  internet_security_enabled = null
  # name - (required) is a type of string
  name = null
  # remote_virtual_network_id - (required) is a type of string
  remote_virtual_network_id = null
  # virtual_hub_id - (required) is a type of string
  virtual_hub_id = null
  # vitual_network_to_hub_gateways_traffic_allowed - (optional) is a type of bool
  vitual_network_to_hub_gateways_traffic_allowed = null

  routing = [{
    associated_route_table_id = null
    propagated_route_table = [{
      labels          = []
      route_table_ids = []
    }]
    static_vnet_route = [{
      address_prefixes    = []
      name                = null
      next_hop_ip_address = null
    }]
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
variable "hub_to_vitual_network_traffic_allowed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "internet_security_enabled" {
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

variable "virtual_hub_id" {
  description = "(required)"
  type        = string
}

variable "vitual_network_to_hub_gateways_traffic_allowed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "routing" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      associated_route_table_id = string
      propagated_route_table = list(object(
        {
          labels          = set(string)
          route_table_ids = list(string)
        }
      ))
      static_vnet_route = list(object(
        {
          address_prefixes    = set(string)
          name                = string
          next_hop_ip_address = string
        }
      ))
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
resource "azurerm_virtual_hub_connection" "this" {
  hub_to_vitual_network_traffic_allowed          = var.hub_to_vitual_network_traffic_allowed
  internet_security_enabled                      = var.internet_security_enabled
  name                                           = var.name
  remote_virtual_network_id                      = var.remote_virtual_network_id
  virtual_hub_id                                 = var.virtual_hub_id
  vitual_network_to_hub_gateways_traffic_allowed = var.vitual_network_to_hub_gateways_traffic_allowed

  dynamic "routing" {
    for_each = var.routing
    content {
      associated_route_table_id = routing.value["associated_route_table_id"]

      dynamic "propagated_route_table" {
        for_each = routing.value.propagated_route_table
        content {
          labels          = propagated_route_table.value["labels"]
          route_table_ids = propagated_route_table.value["route_table_ids"]
        }
      }

      dynamic "static_vnet_route" {
        for_each = routing.value.static_vnet_route
        content {
          address_prefixes    = static_vnet_route.value["address_prefixes"]
          name                = static_vnet_route.value["name"]
          next_hop_ip_address = static_vnet_route.value["next_hop_ip_address"]
        }
      }

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
  value       = azurerm_virtual_hub_connection.this.id
}

output "this" {
  value = azurerm_virtual_hub_connection.this
}
```

[top](#index)