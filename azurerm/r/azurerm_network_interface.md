# azurerm_network_interface

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
module "azurerm_network_interface" {
  source = "./modules/azurerm/r/azurerm_network_interface"

  # dns_servers - (optional) is a type of list of string
  dns_servers = []
  # enable_accelerated_networking - (optional) is a type of bool
  enable_accelerated_networking = null
  # enable_ip_forwarding - (optional) is a type of bool
  enable_ip_forwarding = null
  # internal_dns_name_label - (optional) is a type of string
  internal_dns_name_label = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  ip_configuration = [{
    name                          = null
    primary                       = null
    private_ip_address            = null
    private_ip_address_allocation = null
    private_ip_address_version    = null
    public_ip_address_id          = null
    subnet_id                     = null
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

variable "enable_accelerated_networking" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ip_forwarding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "internal_dns_name_label" {
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ip_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name                          = string
      primary                       = bool
      private_ip_address            = string
      private_ip_address_allocation = string
      private_ip_address_version    = string
      public_ip_address_id          = string
      subnet_id                     = string
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
resource "azurerm_network_interface" "this" {
  # dns_servers - (optional) is a type of list of string
  dns_servers = var.dns_servers
  # enable_accelerated_networking - (optional) is a type of bool
  enable_accelerated_networking = var.enable_accelerated_networking
  # enable_ip_forwarding - (optional) is a type of bool
  enable_ip_forwarding = var.enable_ip_forwarding
  # internal_dns_name_label - (optional) is a type of string
  internal_dns_name_label = var.internal_dns_name_label
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "ip_configuration" {
    for_each = var.ip_configuration
    content {
      # name - (required) is a type of string
      name = ip_configuration.value["name"]
      # primary - (optional) is a type of bool
      primary = ip_configuration.value["primary"]
      # private_ip_address - (optional) is a type of string
      private_ip_address = ip_configuration.value["private_ip_address"]
      # private_ip_address_allocation - (required) is a type of string
      private_ip_address_allocation = ip_configuration.value["private_ip_address_allocation"]
      # private_ip_address_version - (optional) is a type of string
      private_ip_address_version = ip_configuration.value["private_ip_address_version"]
      # public_ip_address_id - (optional) is a type of string
      public_ip_address_id = ip_configuration.value["public_ip_address_id"]
      # subnet_id - (optional) is a type of string
      subnet_id = ip_configuration.value["subnet_id"]
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
output "applied_dns_servers" {
  description = "returns a list of string"
  value       = azurerm_network_interface.this.applied_dns_servers
}

output "dns_servers" {
  description = "returns a list of string"
  value       = azurerm_network_interface.this.dns_servers
}

output "id" {
  description = "returns a string"
  value       = azurerm_network_interface.this.id
}

output "internal_dns_name_label" {
  description = "returns a string"
  value       = azurerm_network_interface.this.internal_dns_name_label
}

output "internal_domain_name_suffix" {
  description = "returns a string"
  value       = azurerm_network_interface.this.internal_domain_name_suffix
}

output "mac_address" {
  description = "returns a string"
  value       = azurerm_network_interface.this.mac_address
}

output "private_ip_address" {
  description = "returns a string"
  value       = azurerm_network_interface.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_network_interface.this.private_ip_addresses
}

output "virtual_machine_id" {
  description = "returns a string"
  value       = azurerm_network_interface.this.virtual_machine_id
}

output "this" {
  value = azurerm_network_interface.this
}
```

[top](#index)