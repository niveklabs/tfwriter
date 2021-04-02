# azurerm_virtual_network

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
module "azurerm_virtual_network" {
  source = "./modules/azurerm/r/azurerm_virtual_network"

  # address_space - (required) is a type of list of string
  address_space = []
  # bgp_community - (optional) is a type of string
  bgp_community = null
  # dns_servers - (optional) is a type of list of string
  dns_servers = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # subnet - (optional) is a type of set of object
  subnet = [{
    address_prefix = null
    id             = null
    name           = null
    security_group = null
  }]
  # tags - (optional) is a type of map of string
  tags = {}
  # vm_protection_enabled - (optional) is a type of bool
  vm_protection_enabled = null

  ddos_protection_plan = [{
    enable = null
    id     = null
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
variable "address_space" {
  description = "(required)"
  type        = list(string)
}

variable "bgp_community" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "subnet" {
  description = "(optional)"
  type = set(object(
    {
      address_prefix = string
      id             = string
      name           = string
      security_group = string
    }
  ))
  default = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vm_protection_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ddos_protection_plan" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable = bool
      id     = string
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
resource "azurerm_virtual_network" "this" {
  address_space         = var.address_space
  bgp_community         = var.bgp_community
  dns_servers           = var.dns_servers
  location              = var.location
  name                  = var.name
  resource_group_name   = var.resource_group_name
  subnet                = var.subnet
  tags                  = var.tags
  vm_protection_enabled = var.vm_protection_enabled

  dynamic "ddos_protection_plan" {
    for_each = var.ddos_protection_plan
    content {
      enable = ddos_protection_plan.value["enable"]
      id     = ddos_protection_plan.value["id"]
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
output "guid" {
  description = "returns a string"
  value       = azurerm_virtual_network.this.guid
}

output "id" {
  description = "returns a string"
  value       = azurerm_virtual_network.this.id
}

output "subnet" {
  description = "returns a set of object"
  value       = azurerm_virtual_network.this.subnet
}

output "this" {
  value = azurerm_virtual_network.this
}
```

[top](#index)