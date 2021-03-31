# azurerm_shared_image_version

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
module "azurerm_shared_image_version" {
  source = "./modules/azurerm/r/azurerm_shared_image_version"

  # exclude_from_latest - (optional) is a type of bool
  exclude_from_latest = null
  # gallery_name - (required) is a type of string
  gallery_name = null
  # image_name - (required) is a type of string
  image_name = null
  # location - (required) is a type of string
  location = null
  # managed_image_id - (optional) is a type of string
  managed_image_id = null
  # name - (required) is a type of string
  name = null
  # os_disk_snapshot_id - (optional) is a type of string
  os_disk_snapshot_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  target_region = [{
    name                   = null
    regional_replica_count = null
    storage_account_type   = null
  }]

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
variable "exclude_from_latest" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "gallery_name" {
  description = "(required)"
  type        = string
}

variable "image_name" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "managed_image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "os_disk_snapshot_id" {
  description = "(optional)"
  type        = string
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

variable "target_region" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      name                   = string
      regional_replica_count = number
      storage_account_type   = string
    }
  ))
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
resource "azurerm_shared_image_version" "this" {
  exclude_from_latest = var.exclude_from_latest
  gallery_name        = var.gallery_name
  image_name          = var.image_name
  location            = var.location
  managed_image_id    = var.managed_image_id
  name                = var.name
  os_disk_snapshot_id = var.os_disk_snapshot_id
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "target_region" {
    for_each = var.target_region
    content {
      name                   = target_region.value["name"]
      regional_replica_count = target_region.value["regional_replica_count"]
      storage_account_type   = target_region.value["storage_account_type"]
    }
  }

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
  value       = azurerm_shared_image_version.this.id
}

output "this" {
  value = azurerm_shared_image_version.this
}
```

[top](#index)