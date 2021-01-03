# azurerm_network_security_rule

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_network_security_rule" {
  source = "./modules/azurerm/r/azurerm_network_security_rule"

  # access - (required) is a type of string
  access = null
  # description - (optional) is a type of string
  description = null
  # destination_address_prefix - (optional) is a type of string
  destination_address_prefix = null
  # destination_address_prefixes - (optional) is a type of set of string
  destination_address_prefixes = []
  # destination_application_security_group_ids - (optional) is a type of set of string
  destination_application_security_group_ids = []
  # destination_port_range - (optional) is a type of string
  destination_port_range = null
  # destination_port_ranges - (optional) is a type of set of string
  destination_port_ranges = []
  # direction - (required) is a type of string
  direction = null
  # name - (required) is a type of string
  name = null
  # network_security_group_name - (required) is a type of string
  network_security_group_name = null
  # priority - (required) is a type of number
  priority = null
  # protocol - (required) is a type of string
  protocol = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_address_prefix - (optional) is a type of string
  source_address_prefix = null
  # source_address_prefixes - (optional) is a type of set of string
  source_address_prefixes = []
  # source_application_security_group_ids - (optional) is a type of set of string
  source_application_security_group_ids = []
  # source_port_range - (optional) is a type of string
  source_port_range = null
  # source_port_ranges - (optional) is a type of set of string
  source_port_ranges = []

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
variable "access" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_address_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_address_prefixes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "destination_application_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "destination_port_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_port_ranges" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "direction" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_security_group_name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source_address_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_address_prefixes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_application_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_port_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_port_ranges" {
  description = "(optional)"
  type        = set(string)
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
resource "azurerm_network_security_rule" "this" {
  access                                     = var.access
  description                                = var.description
  destination_address_prefix                 = var.destination_address_prefix
  destination_address_prefixes               = var.destination_address_prefixes
  destination_application_security_group_ids = var.destination_application_security_group_ids
  destination_port_range                     = var.destination_port_range
  destination_port_ranges                    = var.destination_port_ranges
  direction                                  = var.direction
  name                                       = var.name
  network_security_group_name                = var.network_security_group_name
  priority                                   = var.priority
  protocol                                   = var.protocol
  resource_group_name                        = var.resource_group_name
  source_address_prefix                      = var.source_address_prefix
  source_address_prefixes                    = var.source_address_prefixes
  source_application_security_group_ids      = var.source_application_security_group_ids
  source_port_range                          = var.source_port_range
  source_port_ranges                         = var.source_port_ranges

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
output "id" {
  description = "returns a string"
  value       = azurerm_network_security_rule.this.id
}

output "this" {
  value = azurerm_network_security_rule.this
}
```

[top](#index)