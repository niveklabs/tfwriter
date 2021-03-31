# azurerm_virtual_network_gateway_connection

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_virtual_network_gateway_connection" {
  source = "./modules/azurerm/d/azurerm_virtual_network_gateway_connection"

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
data "azurerm_virtual_network_gateway_connection" "this" {
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
output "authorization_key" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.authorization_key
}

output "connection_protocol" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.connection_protocol
}

output "dpd_timeout_seconds" {
  description = "returns a number"
  value       = data.azurerm_virtual_network_gateway_connection.this.dpd_timeout_seconds
}

output "egress_bytes_transferred" {
  description = "returns a number"
  value       = data.azurerm_virtual_network_gateway_connection.this.egress_bytes_transferred
}

output "enable_bgp" {
  description = "returns a bool"
  value       = data.azurerm_virtual_network_gateway_connection.this.enable_bgp
}

output "express_route_circuit_id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.express_route_circuit_id
}

output "express_route_gateway_bypass" {
  description = "returns a bool"
  value       = data.azurerm_virtual_network_gateway_connection.this.express_route_gateway_bypass
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.id
}

output "ingress_bytes_transferred" {
  description = "returns a number"
  value       = data.azurerm_virtual_network_gateway_connection.this.ingress_bytes_transferred
}

output "ipsec_policy" {
  description = "returns a list of object"
  value       = data.azurerm_virtual_network_gateway_connection.this.ipsec_policy
}

output "local_azure_ip_address_enabled" {
  description = "returns a bool"
  value       = data.azurerm_virtual_network_gateway_connection.this.local_azure_ip_address_enabled
}

output "local_network_gateway_id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.local_network_gateway_id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.location
}

output "peer_virtual_network_gateway_id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.peer_virtual_network_gateway_id
}

output "resource_guid" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.resource_guid
}

output "routing_weight" {
  description = "returns a number"
  value       = data.azurerm_virtual_network_gateway_connection.this.routing_weight
}

output "shared_key" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.shared_key
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_virtual_network_gateway_connection.this.tags
}

output "traffic_selector_policy" {
  description = "returns a list of object"
  value       = data.azurerm_virtual_network_gateway_connection.this.traffic_selector_policy
}

output "type" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.type
}

output "use_policy_based_traffic_selectors" {
  description = "returns a bool"
  value       = data.azurerm_virtual_network_gateway_connection.this.use_policy_based_traffic_selectors
}

output "virtual_network_gateway_id" {
  description = "returns a string"
  value       = data.azurerm_virtual_network_gateway_connection.this.virtual_network_gateway_id
}

output "this" {
  value = azurerm_virtual_network_gateway_connection.this
}
```

[top](#index)