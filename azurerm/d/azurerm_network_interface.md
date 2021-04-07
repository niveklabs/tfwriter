# azurerm_network_interface

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
module "azurerm_network_interface" {
  source = "./modules/azurerm/d/azurerm_network_interface"

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
data "azurerm_network_interface" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "applied_dns_servers" {
  description = "returns a set of string"
  value       = data.azurerm_network_interface.this.applied_dns_servers
}

output "dns_servers" {
  description = "returns a set of string"
  value       = data.azurerm_network_interface.this.dns_servers
}

output "enable_accelerated_networking" {
  description = "returns a bool"
  value       = data.azurerm_network_interface.this.enable_accelerated_networking
}

output "enable_ip_forwarding" {
  description = "returns a bool"
  value       = data.azurerm_network_interface.this.enable_ip_forwarding
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_network_interface.this.id
}

output "internal_dns_name_label" {
  description = "returns a string"
  value       = data.azurerm_network_interface.this.internal_dns_name_label
}

output "ip_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_network_interface.this.ip_configuration
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_network_interface.this.location
}

output "mac_address" {
  description = "returns a string"
  value       = data.azurerm_network_interface.this.mac_address
}

output "network_security_group_id" {
  description = "returns a string"
  value       = data.azurerm_network_interface.this.network_security_group_id
}

output "private_ip_address" {
  description = "returns a string"
  value       = data.azurerm_network_interface.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_network_interface.this.private_ip_addresses
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_network_interface.this.tags
}

output "virtual_machine_id" {
  description = "returns a string"
  value       = data.azurerm_network_interface.this.virtual_machine_id
}

output "this" {
  value = azurerm_network_interface.this
}
```

[top](#index)