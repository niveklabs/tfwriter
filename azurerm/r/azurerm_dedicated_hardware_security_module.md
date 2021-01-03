# azurerm_dedicated_hardware_security_module

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
module "azurerm_dedicated_hardware_security_module" {
  source = "./modules/azurerm/r/azurerm_dedicated_hardware_security_module"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # stamp_id - (optional) is a type of string
  stamp_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

  network_profile = [{
    network_interface_private_ip_addresses = []
    subnet_id                              = null
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

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "stamp_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "network_profile" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      network_interface_private_ip_addresses = set(string)
      subnet_id                              = string
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
resource "azurerm_dedicated_hardware_security_module" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  sku_name            = var.sku_name
  stamp_id            = var.stamp_id
  tags                = var.tags
  zones               = var.zones

  dynamic "network_profile" {
    for_each = var.network_profile
    content {
      network_interface_private_ip_addresses = network_profile.value["network_interface_private_ip_addresses"]
      subnet_id                              = network_profile.value["subnet_id"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_dedicated_hardware_security_module.this.id
}

output "this" {
  value = azurerm_dedicated_hardware_security_module.this
}
```

[top](#index)