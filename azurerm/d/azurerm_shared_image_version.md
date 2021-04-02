# azurerm_shared_image_version

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
module "azurerm_shared_image_version" {
  source = "./modules/azurerm/d/azurerm_shared_image_version"

  # gallery_name - (required) is a type of string
  gallery_name = null
  # image_name - (required) is a type of string
  image_name = null
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

variable "image_name" {
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
data "azurerm_shared_image_version" "this" {
  gallery_name        = var.gallery_name
  image_name          = var.image_name
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
output "exclude_from_latest" {
  description = "returns a bool"
  value       = data.azurerm_shared_image_version.this.exclude_from_latest
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_shared_image_version.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_shared_image_version.this.location
}

output "managed_image_id" {
  description = "returns a string"
  value       = data.azurerm_shared_image_version.this.managed_image_id
}

output "os_disk_image_size_gb" {
  description = "returns a number"
  value       = data.azurerm_shared_image_version.this.os_disk_image_size_gb
}

output "os_disk_snapshot_id" {
  description = "returns a string"
  value       = data.azurerm_shared_image_version.this.os_disk_snapshot_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_shared_image_version.this.tags
}

output "target_region" {
  description = "returns a list of object"
  value       = data.azurerm_shared_image_version.this.target_region
}

output "this" {
  value = azurerm_shared_image_version.this
}
```

[top](#index)