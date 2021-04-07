# azurerm_private_dns_zone_virtual_network_link

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
module "azurerm_private_dns_zone_virtual_network_link" {
  source = "./modules/azurerm/r/azurerm_private_dns_zone_virtual_network_link"

  # name - (required) is a type of string
  name = null
  # private_dns_zone_name - (required) is a type of string
  private_dns_zone_name = null
  # registration_enabled - (optional) is a type of bool
  registration_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_network_id - (required) is a type of string
  virtual_network_id = null

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
variable "name" {
  description = "(required)"
  type        = string
}

variable "private_dns_zone_name" {
  description = "(required)"
  type        = string
}

variable "registration_enabled" {
  description = "(optional)"
  type        = bool
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

variable "virtual_network_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_private_dns_zone_virtual_network_link" "this" {
  # name - (required) is a type of string
  name = var.name
  # private_dns_zone_name - (required) is a type of string
  private_dns_zone_name = var.private_dns_zone_name
  # registration_enabled - (optional) is a type of bool
  registration_enabled = var.registration_enabled
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # virtual_network_id - (required) is a type of string
  virtual_network_id = var.virtual_network_id

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
  value       = azurerm_private_dns_zone_virtual_network_link.this.id
}

output "this" {
  value = azurerm_private_dns_zone_virtual_network_link.this
}
```

[top](#index)