# azurestack_virtual_network_gateway

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurestack_virtual_network_gateway" {
  source = "./modules/azurestack/d/azurestack_virtual_network_gateway"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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
```

[top](#index)

### Datasource

```terraform
data "azurestack_virtual_network_gateway" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "bgp_settings" {
  description = "returns a list of object"
  value       = data.azurestack_virtual_network_gateway.this.bgp_settings
}

output "default_local_network_gateway_id" {
  description = "returns a string"
  value       = data.azurestack_virtual_network_gateway.this.default_local_network_gateway_id
}

output "enable_bgp" {
  description = "returns a bool"
  value       = data.azurestack_virtual_network_gateway.this.enable_bgp
}

output "id" {
  description = "returns a string"
  value       = data.azurestack_virtual_network_gateway.this.id
}

output "ip_configuration" {
  description = "returns a list of object"
  value       = data.azurestack_virtual_network_gateway.this.ip_configuration
}

output "location" {
  description = "returns a string"
  value       = data.azurestack_virtual_network_gateway.this.location
}

output "sku" {
  description = "returns a string"
  value       = data.azurestack_virtual_network_gateway.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurestack_virtual_network_gateway.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.azurestack_virtual_network_gateway.this.type
}

output "vpn_client_configuration" {
  description = "returns a list of object"
  value       = data.azurestack_virtual_network_gateway.this.vpn_client_configuration
}

output "vpn_type" {
  description = "returns a string"
  value       = data.azurestack_virtual_network_gateway.this.vpn_type
}

output "this" {
  value = azurestack_virtual_network_gateway.this
}
```

[top](#index)