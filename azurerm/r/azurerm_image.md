# azurerm_image

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
module "azurerm_image" {
  source = "./modules/azurerm/r/azurerm_image"

  # hyper_v_generation - (optional) is a type of string
  hyper_v_generation = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_virtual_machine_id - (optional) is a type of string
  source_virtual_machine_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone_resilient - (optional) is a type of bool
  zone_resilient = null

  data_disk = [{
    blob_uri        = null
    caching         = null
    lun             = null
    managed_disk_id = null
    size_gb         = null
  }]

  os_disk = [{
    blob_uri        = null
    caching         = null
    managed_disk_id = null
    os_state        = null
    os_type         = null
    size_gb         = null
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
variable "hyper_v_generation" {
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

variable "source_virtual_machine_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zone_resilient" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "data_disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      blob_uri        = string
      caching         = string
      lun             = number
      managed_disk_id = string
      size_gb         = number
    }
  ))
  default = []
}

variable "os_disk" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      blob_uri        = string
      caching         = string
      managed_disk_id = string
      os_state        = string
      os_type         = string
      size_gb         = number
    }
  ))
  default = []
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
resource "azurerm_image" "this" {
  hyper_v_generation        = var.hyper_v_generation
  location                  = var.location
  name                      = var.name
  resource_group_name       = var.resource_group_name
  source_virtual_machine_id = var.source_virtual_machine_id
  tags                      = var.tags
  zone_resilient            = var.zone_resilient

  dynamic "data_disk" {
    for_each = var.data_disk
    content {
      blob_uri        = data_disk.value["blob_uri"]
      caching         = data_disk.value["caching"]
      lun             = data_disk.value["lun"]
      managed_disk_id = data_disk.value["managed_disk_id"]
      size_gb         = data_disk.value["size_gb"]
    }
  }

  dynamic "os_disk" {
    for_each = var.os_disk
    content {
      blob_uri        = os_disk.value["blob_uri"]
      caching         = os_disk.value["caching"]
      managed_disk_id = os_disk.value["managed_disk_id"]
      os_state        = os_disk.value["os_state"]
      os_type         = os_disk.value["os_type"]
      size_gb         = os_disk.value["size_gb"]
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
  value       = azurerm_image.this.id
}

output "this" {
  value = azurerm_image.this
}
```

[top](#index)