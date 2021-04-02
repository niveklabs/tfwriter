# azurerm_virtual_wan

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
module "azurerm_virtual_wan" {
  source = "./modules/azurerm/r/azurerm_virtual_wan"

  # allow_branch_to_branch_traffic - (optional) is a type of bool
  allow_branch_to_branch_traffic = null
  # allow_vnet_to_vnet_traffic - (optional) is a type of bool
  allow_vnet_to_vnet_traffic = null
  # disable_vpn_encryption - (optional) is a type of bool
  disable_vpn_encryption = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # office365_local_breakout_category - (optional) is a type of string
  office365_local_breakout_category = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null

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
variable "allow_branch_to_branch_traffic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_vnet_to_vnet_traffic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_vpn_encryption" {
  description = "(optional)"
  type        = bool
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

variable "office365_local_breakout_category" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "type" {
  description = "(optional)"
  type        = string
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
resource "azurerm_virtual_wan" "this" {
  allow_branch_to_branch_traffic    = var.allow_branch_to_branch_traffic
  allow_vnet_to_vnet_traffic        = var.allow_vnet_to_vnet_traffic
  disable_vpn_encryption            = var.disable_vpn_encryption
  location                          = var.location
  name                              = var.name
  office365_local_breakout_category = var.office365_local_breakout_category
  resource_group_name               = var.resource_group_name
  tags                              = var.tags
  type                              = var.type

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
  value       = azurerm_virtual_wan.this.id
}

output "this" {
  value = azurerm_virtual_wan.this
}
```

[top](#index)