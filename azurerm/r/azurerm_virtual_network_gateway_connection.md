# azurerm_virtual_network_gateway_connection

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
module "azurerm_virtual_network_gateway_connection" {
  source = "./modules/azurerm/r/azurerm_virtual_network_gateway_connection"

  # authorization_key - (optional) is a type of string
  authorization_key = null
  # connection_protocol - (optional) is a type of string
  connection_protocol = null
  # dpd_timeout_seconds - (optional) is a type of number
  dpd_timeout_seconds = null
  # enable_bgp - (optional) is a type of bool
  enable_bgp = null
  # express_route_circuit_id - (optional) is a type of string
  express_route_circuit_id = null
  # express_route_gateway_bypass - (optional) is a type of bool
  express_route_gateway_bypass = null
  # local_azure_ip_address_enabled - (optional) is a type of bool
  local_azure_ip_address_enabled = null
  # local_network_gateway_id - (optional) is a type of string
  local_network_gateway_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # peer_virtual_network_gateway_id - (optional) is a type of string
  peer_virtual_network_gateway_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # routing_weight - (optional) is a type of number
  routing_weight = null
  # shared_key - (optional) is a type of string
  shared_key = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
  # use_policy_based_traffic_selectors - (optional) is a type of bool
  use_policy_based_traffic_selectors = null
  # virtual_network_gateway_id - (required) is a type of string
  virtual_network_gateway_id = null

  ipsec_policy = [{
    dh_group         = null
    ike_encryption   = null
    ike_integrity    = null
    ipsec_encryption = null
    ipsec_integrity  = null
    pfs_group        = null
    sa_datasize      = null
    sa_lifetime      = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  traffic_selector_policy = [{
    local_address_cidrs  = []
    remote_address_cidrs = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorization_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dpd_timeout_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_bgp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "express_route_circuit_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "express_route_gateway_bypass" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "local_azure_ip_address_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "local_network_gateway_id" {
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

variable "peer_virtual_network_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "routing_weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "use_policy_based_traffic_selectors" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "virtual_network_gateway_id" {
  description = "(required)"
  type        = string
}

variable "ipsec_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dh_group         = string
      ike_encryption   = string
      ike_integrity    = string
      ipsec_encryption = string
      ipsec_integrity  = string
      pfs_group        = string
      sa_datasize      = number
      sa_lifetime      = number
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

variable "traffic_selector_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      local_address_cidrs  = list(string)
      remote_address_cidrs = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_virtual_network_gateway_connection" "this" {
  authorization_key                  = var.authorization_key
  connection_protocol                = var.connection_protocol
  dpd_timeout_seconds                = var.dpd_timeout_seconds
  enable_bgp                         = var.enable_bgp
  express_route_circuit_id           = var.express_route_circuit_id
  express_route_gateway_bypass       = var.express_route_gateway_bypass
  local_azure_ip_address_enabled     = var.local_azure_ip_address_enabled
  local_network_gateway_id           = var.local_network_gateway_id
  location                           = var.location
  name                               = var.name
  peer_virtual_network_gateway_id    = var.peer_virtual_network_gateway_id
  resource_group_name                = var.resource_group_name
  routing_weight                     = var.routing_weight
  shared_key                         = var.shared_key
  tags                               = var.tags
  type                               = var.type
  use_policy_based_traffic_selectors = var.use_policy_based_traffic_selectors
  virtual_network_gateway_id         = var.virtual_network_gateway_id

  dynamic "ipsec_policy" {
    for_each = var.ipsec_policy
    content {
      dh_group         = ipsec_policy.value["dh_group"]
      ike_encryption   = ipsec_policy.value["ike_encryption"]
      ike_integrity    = ipsec_policy.value["ike_integrity"]
      ipsec_encryption = ipsec_policy.value["ipsec_encryption"]
      ipsec_integrity  = ipsec_policy.value["ipsec_integrity"]
      pfs_group        = ipsec_policy.value["pfs_group"]
      sa_datasize      = ipsec_policy.value["sa_datasize"]
      sa_lifetime      = ipsec_policy.value["sa_lifetime"]
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

  dynamic "traffic_selector_policy" {
    for_each = var.traffic_selector_policy
    content {
      local_address_cidrs  = traffic_selector_policy.value["local_address_cidrs"]
      remote_address_cidrs = traffic_selector_policy.value["remote_address_cidrs"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "connection_protocol" {
  description = "returns a string"
  value       = azurerm_virtual_network_gateway_connection.this.connection_protocol
}

output "enable_bgp" {
  description = "returns a bool"
  value       = azurerm_virtual_network_gateway_connection.this.enable_bgp
}

output "express_route_gateway_bypass" {
  description = "returns a bool"
  value       = azurerm_virtual_network_gateway_connection.this.express_route_gateway_bypass
}

output "id" {
  description = "returns a string"
  value       = azurerm_virtual_network_gateway_connection.this.id
}

output "routing_weight" {
  description = "returns a number"
  value       = azurerm_virtual_network_gateway_connection.this.routing_weight
}

output "use_policy_based_traffic_selectors" {
  description = "returns a bool"
  value       = azurerm_virtual_network_gateway_connection.this.use_policy_based_traffic_selectors
}

output "this" {
  value = azurerm_virtual_network_gateway_connection.this
}
```

[top](#index)