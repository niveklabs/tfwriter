# azurerm_images

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_images" {
  source = "./modules/azurerm/d/azurerm_images"

  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags_filter - (optional) is a type of map of string
  tags_filter = {}

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags_filter" {
  description = "(optional)"
  type        = map(string)
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
data "azurerm_images" "this" {
  resource_group_name = var.resource_group_name
  tags_filter         = var.tags_filter

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
  value       = data.azurerm_images.this.id
}

output "images" {
  description = "returns a list of object"
  value       = data.azurerm_images.this.images
}

output "this" {
  value = azurerm_images.this
}
```

[top](#index)