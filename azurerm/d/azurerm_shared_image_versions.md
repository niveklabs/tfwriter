# azurerm_shared_image_versions

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
module "azurerm_shared_image_versions" {
  source = "./modules/azurerm/d/azurerm_shared_image_versions"

  # gallery_name - (required) is a type of string
  gallery_name = null
  # image_name - (required) is a type of string
  image_name = null
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
variable "gallery_name" {
  description = "(required)"
  type        = string
}

variable "image_name" {
  description = "(required)"
  type        = string
}

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
data "azurerm_shared_image_versions" "this" {
  gallery_name        = var.gallery_name
  image_name          = var.image_name
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
  value       = data.azurerm_shared_image_versions.this.id
}

output "images" {
  description = "returns a list of object"
  value       = data.azurerm_shared_image_versions.this.images
}

output "this" {
  value = azurerm_shared_image_versions.this
}
```

[top](#index)