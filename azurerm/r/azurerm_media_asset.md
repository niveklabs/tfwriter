# azurerm_media_asset

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
module "azurerm_media_asset" {
  source = "./modules/azurerm/r/azurerm_media_asset"

  # alternate_id - (optional) is a type of string
  alternate_id = null
  # container - (optional) is a type of string
  container = null
  # description - (optional) is a type of string
  description = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_name - (optional) is a type of string
  storage_account_name = null

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
variable "alternate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "container" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "media_services_account_name" {
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

variable "storage_account_name" {
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
resource "azurerm_media_asset" "this" {
  alternate_id                = var.alternate_id
  container                   = var.container
  description                 = var.description
  media_services_account_name = var.media_services_account_name
  name                        = var.name
  resource_group_name         = var.resource_group_name
  storage_account_name        = var.storage_account_name

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
output "container" {
  description = "returns a string"
  value       = azurerm_media_asset.this.container
}

output "id" {
  description = "returns a string"
  value       = azurerm_media_asset.this.id
}

output "storage_account_name" {
  description = "returns a string"
  value       = azurerm_media_asset.this.storage_account_name
}

output "this" {
  value = azurerm_media_asset.this
}
```

[top](#index)