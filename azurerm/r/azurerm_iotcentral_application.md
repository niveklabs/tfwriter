# azurerm_iotcentral_application

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
module "azurerm_iotcentral_application" {
  source = "./modules/azurerm/r/azurerm_iotcentral_application"

  # display_name - (optional) is a type of string
  display_name = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (optional) is a type of string
  sku = null
  # sub_domain - (required) is a type of string
  sub_domain = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template - (optional) is a type of string
  template = null

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
variable "display_name" {
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

variable "sku" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sub_domain" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template" {
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
resource "azurerm_iotcentral_application" "this" {
  display_name        = var.display_name
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  sku                 = var.sku
  sub_domain          = var.sub_domain
  tags                = var.tags
  template            = var.template

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
output "display_name" {
  description = "returns a string"
  value       = azurerm_iotcentral_application.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_iotcentral_application.this.id
}

output "template" {
  description = "returns a string"
  value       = azurerm_iotcentral_application.this.template
}

output "this" {
  value = azurerm_iotcentral_application.this
}
```

[top](#index)