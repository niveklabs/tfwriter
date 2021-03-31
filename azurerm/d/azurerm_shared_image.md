# azurerm_shared_image

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
module "azurerm_shared_image" {
  source = "./modules/azurerm/d/azurerm_shared_image"

  # gallery_name - (required) is a type of string
  gallery_name = null
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
variable "gallery_name" {
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
data "azurerm_shared_image" "this" {
  gallery_name        = var.gallery_name
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
output "description" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.description
}

output "eula" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.eula
}

output "hyper_v_generation" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.hyper_v_generation
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.id
}

output "identifier" {
  description = "returns a list of object"
  value       = data.azurerm_shared_image.this.identifier
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.location
}

output "os_type" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.os_type
}

output "privacy_statement_uri" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.privacy_statement_uri
}

output "release_note_uri" {
  description = "returns a string"
  value       = data.azurerm_shared_image.this.release_note_uri
}

output "specialized" {
  description = "returns a bool"
  value       = data.azurerm_shared_image.this.specialized
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_shared_image.this.tags
}

output "this" {
  value = azurerm_shared_image.this
}
```

[top](#index)