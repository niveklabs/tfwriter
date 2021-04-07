# azurestack_virtual_network_gateway_connection

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_virtual_network_gateway_connection" {
  source = "./modules/azurestack/r/azurestack_virtual_network_gateway_connection"

  # authorization_key - (optional) is a type of string
  authorization_key = null
  # enable_bgp - (optional) is a type of bool
  enable_bgp = null
  # express_route_circuit_id - (optional) is a type of string
  express_route_circuit_id = null
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
  # virtual_network_gateway_id - (required) is a type of string
  virtual_network_gateway_id = null
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

variable "virtual_network_gateway_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_virtual_network_gateway_connection" "this" {
  # authorization_key - (optional) is a type of string
  authorization_key = var.authorization_key
  # enable_bgp - (optional) is a type of bool
  enable_bgp = var.enable_bgp
  # express_route_circuit_id - (optional) is a type of string
  express_route_circuit_id = var.express_route_circuit_id
  # local_network_gateway_id - (optional) is a type of string
  local_network_gateway_id = var.local_network_gateway_id
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # peer_virtual_network_gateway_id - (optional) is a type of string
  peer_virtual_network_gateway_id = var.peer_virtual_network_gateway_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # routing_weight - (optional) is a type of number
  routing_weight = var.routing_weight
  # shared_key - (optional) is a type of string
  shared_key = var.shared_key
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type
  # virtual_network_gateway_id - (required) is a type of string
  virtual_network_gateway_id = var.virtual_network_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "enable_bgp" {
  description = "returns a bool"
  value       = azurestack_virtual_network_gateway_connection.this.enable_bgp
}

output "id" {
  description = "returns a string"
  value       = azurestack_virtual_network_gateway_connection.this.id
}

output "routing_weight" {
  description = "returns a number"
  value       = azurestack_virtual_network_gateway_connection.this.routing_weight
}

output "shared_key" {
  description = "returns a string"
  value       = azurestack_virtual_network_gateway_connection.this.shared_key
  sensitive   = true
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_virtual_network_gateway_connection.this.tags
}

output "this" {
  value = azurestack_virtual_network_gateway_connection.this
}
```

[top](#index)