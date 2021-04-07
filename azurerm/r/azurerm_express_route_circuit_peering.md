# azurerm_express_route_circuit_peering

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
module "azurerm_express_route_circuit_peering" {
  source = "./modules/azurerm/r/azurerm_express_route_circuit_peering"

  # express_route_circuit_name - (required) is a type of string
  express_route_circuit_name = null
  # peer_asn - (optional) is a type of number
  peer_asn = null
  # peering_type - (required) is a type of string
  peering_type = null
  # primary_peer_address_prefix - (required) is a type of string
  primary_peer_address_prefix = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # route_filter_id - (optional) is a type of string
  route_filter_id = null
  # secondary_peer_address_prefix - (required) is a type of string
  secondary_peer_address_prefix = null
  # shared_key - (optional) is a type of string
  shared_key = null
  # vlan_id - (required) is a type of number
  vlan_id = null

  ipv6 = [{
    microsoft_peering = [{
      advertised_public_prefixes = []
      customer_asn               = null
      routing_registry_name      = null
    }]
    primary_peer_address_prefix   = null
    route_filter_id               = null
    secondary_peer_address_prefix = null
  }]

  microsoft_peering_config = [{
    advertised_public_prefixes = []
    customer_asn               = null
    routing_registry_name      = null
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
variable "express_route_circuit_name" {
  description = "(required)"
  type        = string
}

variable "peer_asn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "peering_type" {
  description = "(required)"
  type        = string
}

variable "primary_peer_address_prefix" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "route_filter_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_peer_address_prefix" {
  description = "(required)"
  type        = string
}

variable "shared_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(required)"
  type        = number
}

variable "ipv6" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      microsoft_peering = list(object(
        {
          advertised_public_prefixes = list(string)
          customer_asn               = number
          routing_registry_name      = string
        }
      ))
      primary_peer_address_prefix   = string
      route_filter_id               = string
      secondary_peer_address_prefix = string
    }
  ))
  default = []
}

variable "microsoft_peering_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      advertised_public_prefixes = list(string)
      customer_asn               = number
      routing_registry_name      = string
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
resource "azurerm_express_route_circuit_peering" "this" {
  # express_route_circuit_name - (required) is a type of string
  express_route_circuit_name = var.express_route_circuit_name
  # peer_asn - (optional) is a type of number
  peer_asn = var.peer_asn
  # peering_type - (required) is a type of string
  peering_type = var.peering_type
  # primary_peer_address_prefix - (required) is a type of string
  primary_peer_address_prefix = var.primary_peer_address_prefix
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # route_filter_id - (optional) is a type of string
  route_filter_id = var.route_filter_id
  # secondary_peer_address_prefix - (required) is a type of string
  secondary_peer_address_prefix = var.secondary_peer_address_prefix
  # shared_key - (optional) is a type of string
  shared_key = var.shared_key
  # vlan_id - (required) is a type of number
  vlan_id = var.vlan_id

  dynamic "ipv6" {
    for_each = var.ipv6
    content {
      # primary_peer_address_prefix - (required) is a type of string
      primary_peer_address_prefix = ipv6.value["primary_peer_address_prefix"]
      # route_filter_id - (optional) is a type of string
      route_filter_id = ipv6.value["route_filter_id"]
      # secondary_peer_address_prefix - (required) is a type of string
      secondary_peer_address_prefix = ipv6.value["secondary_peer_address_prefix"]

      dynamic "microsoft_peering" {
        for_each = ipv6.value.microsoft_peering
        content {
          # advertised_public_prefixes - (optional) is a type of list of string
          advertised_public_prefixes = microsoft_peering.value["advertised_public_prefixes"]
          # customer_asn - (optional) is a type of number
          customer_asn = microsoft_peering.value["customer_asn"]
          # routing_registry_name - (optional) is a type of string
          routing_registry_name = microsoft_peering.value["routing_registry_name"]
        }
      }

    }
  }

  dynamic "microsoft_peering_config" {
    for_each = var.microsoft_peering_config
    content {
      # advertised_public_prefixes - (required) is a type of list of string
      advertised_public_prefixes = microsoft_peering_config.value["advertised_public_prefixes"]
      # customer_asn - (optional) is a type of number
      customer_asn = microsoft_peering_config.value["customer_asn"]
      # routing_registry_name - (optional) is a type of string
      routing_registry_name = microsoft_peering_config.value["routing_registry_name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "azure_asn" {
  description = "returns a number"
  value       = azurerm_express_route_circuit_peering.this.azure_asn
}

output "id" {
  description = "returns a string"
  value       = azurerm_express_route_circuit_peering.this.id
}

output "peer_asn" {
  description = "returns a number"
  value       = azurerm_express_route_circuit_peering.this.peer_asn
}

output "primary_azure_port" {
  description = "returns a string"
  value       = azurerm_express_route_circuit_peering.this.primary_azure_port
}

output "secondary_azure_port" {
  description = "returns a string"
  value       = azurerm_express_route_circuit_peering.this.secondary_azure_port
}

output "this" {
  value = azurerm_express_route_circuit_peering.this
}
```

[top](#index)