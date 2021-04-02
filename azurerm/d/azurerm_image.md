# azurerm_image

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_image" {
  source = "./modules/azurerm/d/azurerm_image"

  # name - (optional) is a type of string
  name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sort_descending - (optional) is a type of bool
  sort_descending = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sort_descending" {
  description = "(optional)"
  type        = bool
  default     = null
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
data "azurerm_image" "this" {
  name                = var.name
  name_regex          = var.name_regex
  resource_group_name = var.resource_group_name
  sort_descending     = var.sort_descending

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
output "data_disk" {
  description = "returns a list of object"
  value       = data.azurerm_image.this.data_disk
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_image.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_image.this.location
}

output "os_disk" {
  description = "returns a list of object"
  value       = data.azurerm_image.this.os_disk
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_image.this.tags
}

output "zone_resilient" {
  description = "returns a bool"
  value       = data.azurerm_image.this.zone_resilient
}

output "this" {
  value = azurerm_image.this
}
```

[top](#index)