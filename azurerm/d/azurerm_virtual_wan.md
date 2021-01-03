# azurerm_virtual_wan

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_virtual_wan" {
  source = "./modules/azurerm/d/azurerm_virtual_wan"

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
data "azurerm_virtual_wan" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_branch_to_branch_traffic" {
  description = "returns a bool"
  value       = data.azurerm_virtual_wan.this.allow_branch_to_branch_traffic
}

output "disable_vpn_encryption" {
  description = "returns a bool"
  value       = data.azurerm_virtual_wan.this.disable_vpn_encryption
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_virtual_wan.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_virtual_wan.this.location
}

output "office365_local_breakout_category" {
  description = "returns a string"
  value       = data.azurerm_virtual_wan.this.office365_local_breakout_category
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_virtual_wan.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_virtual_wan.this.tags
}

output "virtual_hub_ids" {
  description = "returns a list of string"
  value       = data.azurerm_virtual_wan.this.virtual_hub_ids
}

output "vpn_site_ids" {
  description = "returns a list of string"
  value       = data.azurerm_virtual_wan.this.vpn_site_ids
}

output "this" {
  value = azurerm_virtual_wan.this
}
```

[top](#index)