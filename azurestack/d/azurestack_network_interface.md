# azurestack_network_interface

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
module "azurestack_network_interface" {
  source = "./modules/azurestack/d/azurestack_network_interface"

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
data "azurestack_network_interface" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "applied_dns_servers" {
  description = "returns a set of string"
  value       = data.azurestack_network_interface.this.applied_dns_servers
}

output "dns_servers" {
  description = "returns a set of string"
  value       = data.azurestack_network_interface.this.dns_servers
}

output "enable_ip_forwarding" {
  description = "returns a bool"
  value       = data.azurestack_network_interface.this.enable_ip_forwarding
}

output "id" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.id
}

output "internal_dns_name_label" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.internal_dns_name_label
}

output "internal_fqdn" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.internal_fqdn
}

output "ip_configuration" {
  description = "returns a list of object"
  value       = data.azurestack_network_interface.this.ip_configuration
}

output "location" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.location
}

output "mac_address" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.mac_address
}

output "network_security_group_id" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.network_security_group_id
}

output "private_ip_address" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurestack_network_interface.this.private_ip_addresses
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurestack_network_interface.this.tags
}

output "virtual_machine_id" {
  description = "returns a string"
  value       = data.azurestack_network_interface.this.virtual_machine_id
}

output "this" {
  value = azurestack_network_interface.this
}
```

[top](#index)