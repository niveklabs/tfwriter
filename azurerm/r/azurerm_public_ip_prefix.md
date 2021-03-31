# azurerm_public_ip_prefix

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_public_ip_prefix" {
  source = "./modules/azurerm/r/azurerm_public_ip_prefix"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # prefix_length - (optional) is a type of number
  prefix_length = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (optional) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

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

variable "prefix_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku" {
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
resource "azurerm_public_ip_prefix" "this" {
  location            = var.location
  name                = var.name
  prefix_length       = var.prefix_length
  resource_group_name = var.resource_group_name
  sku                 = var.sku
  tags                = var.tags
  zones               = var.zones

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
  value       = azurerm_public_ip_prefix.this.id
}

output "ip_prefix" {
  description = "returns a string"
  value       = azurerm_public_ip_prefix.this.ip_prefix
}

output "this" {
  value = azurerm_public_ip_prefix.this
}
```

[top](#index)