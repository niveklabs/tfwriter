# azurerm_network_security_group

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
module "azurerm_network_security_group" {
  source = "./modules/azurerm/r/azurerm_network_security_group"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # security_rule - (optional) is a type of set of object
  security_rule = [{
    access                                     = null
    description                                = null
    destination_address_prefix                 = null
    destination_address_prefixes               = []
    destination_application_security_group_ids = []
    destination_port_range                     = null
    destination_port_ranges                    = []
    direction                                  = null
    name                                       = null
    priority                                   = null
    protocol                                   = null
    source_address_prefix                      = null
    source_address_prefixes                    = []
    source_application_security_group_ids      = []
    source_port_range                          = null
    source_port_ranges                         = []
  }]
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "security_rule" {
  description = "(optional)"
  type = set(object(
    {
      access                                     = string
      description                                = string
      destination_address_prefix                 = string
      destination_address_prefixes               = set(string)
      destination_application_security_group_ids = set(string)
      destination_port_range                     = string
      destination_port_ranges                    = set(string)
      direction                                  = string
      name                                       = string
      priority                                   = number
      protocol                                   = string
      source_address_prefix                      = string
      source_address_prefixes                    = set(string)
      source_application_security_group_ids      = set(string)
      source_port_range                          = string
      source_port_ranges                         = set(string)
    }
  ))
  default = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
resource "azurerm_network_security_group" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # security_rule - (optional) is a type of set of object
  security_rule = var.security_rule
  # tags - (optional) is a type of map of string
  tags = var.tags

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
output "id" {
  description = "returns a string"
  value       = azurerm_network_security_group.this.id
}

output "security_rule" {
  description = "returns a set of object"
  value       = azurerm_network_security_group.this.security_rule
}

output "this" {
  value = azurerm_network_security_group.this
}
```

[top](#index)