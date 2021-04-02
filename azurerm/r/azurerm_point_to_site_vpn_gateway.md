# azurerm_point_to_site_vpn_gateway

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
module "azurerm_point_to_site_vpn_gateway" {
  source = "./modules/azurerm/r/azurerm_point_to_site_vpn_gateway"

  # dns_servers - (optional) is a type of list of string
  dns_servers = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scale_unit - (required) is a type of number
  scale_unit = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_hub_id - (required) is a type of string
  virtual_hub_id = null
  # vpn_server_configuration_id - (required) is a type of string
  vpn_server_configuration_id = null

  connection_configuration = [{
    name = null
    route = [{
      associated_route_table_id = null
      propagated_route_table = [{
        ids    = []
        labels = []
      }]
    }]
    vpn_client_address_pool = [{
      address_prefixes = []
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
variable "dns_servers" {
  description = "(optional)"
  type        = list(string)
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

variable "scale_unit" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_hub_id" {
  description = "(required)"
  type        = string
}

variable "vpn_server_configuration_id" {
  description = "(required)"
  type        = string
}

variable "connection_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      name = string
      route = list(object(
        {
          associated_route_table_id = string
          propagated_route_table = list(object(
            {
              ids    = list(string)
              labels = set(string)
            }
          ))
        }
      ))
      vpn_client_address_pool = list(object(
        {
          address_prefixes = set(string)
        }
      ))
    }
  ))
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
resource "azurerm_point_to_site_vpn_gateway" "this" {
  dns_servers                 = var.dns_servers
  location                    = var.location
  name                        = var.name
  resource_group_name         = var.resource_group_name
  scale_unit                  = var.scale_unit
  tags                        = var.tags
  virtual_hub_id              = var.virtual_hub_id
  vpn_server_configuration_id = var.vpn_server_configuration_id

  dynamic "connection_configuration" {
    for_each = var.connection_configuration
    content {
      name = connection_configuration.value["name"]

      dynamic "route" {
        for_each = connection_configuration.value.route
        content {
          associated_route_table_id = route.value["associated_route_table_id"]

          dynamic "propagated_route_table" {
            for_each = route.value.propagated_route_table
            content {
              ids    = propagated_route_table.value["ids"]
              labels = propagated_route_table.value["labels"]
            }
          }

        }
      }

      dynamic "vpn_client_address_pool" {
        for_each = connection_configuration.value.vpn_client_address_pool
        content {
          address_prefixes = vpn_client_address_pool.value["address_prefixes"]
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
  value       = azurerm_point_to_site_vpn_gateway.this.id
}

output "this" {
  value = azurerm_point_to_site_vpn_gateway.this
}
```

[top](#index)