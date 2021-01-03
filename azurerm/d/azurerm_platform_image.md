# azurerm_platform_image

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
module "azurerm_platform_image" {
  source = "./modules/azurerm/d/azurerm_platform_image"

  # location - (required) is a type of string
  location = null
  # offer - (required) is a type of string
  offer = null
  # publisher - (required) is a type of string
  publisher = null
  # sku - (required) is a type of string
  sku = null
  # version - (optional) is a type of string
  version = null

  timeouts = [{
    read = null
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

variable "offer" {
  description = "(required)"
  type        = string
}

variable "publisher" {
  description = "(required)"
  type        = string
}

variable "sku" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
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
data "azurerm_platform_image" "this" {
  location  = var.location
  offer     = var.offer
  publisher = var.publisher
  sku       = var.sku
  version   = var.version

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_platform_image.this.id
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_platform_image.this.version
}

output "this" {
  value = azurerm_platform_image.this
}
```

[top](#index)