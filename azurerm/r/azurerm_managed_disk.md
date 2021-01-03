# azurerm_managed_disk

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
module "azurerm_managed_disk" {
  source = "./modules/azurerm/r/azurerm_managed_disk"

  # create_option - (required) is a type of string
  create_option = null
  # disk_encryption_set_id - (optional) is a type of string
  disk_encryption_set_id = null
  # disk_iops_read_write - (optional) is a type of number
  disk_iops_read_write = null
  # disk_mbps_read_write - (optional) is a type of number
  disk_mbps_read_write = null
  # disk_size_gb - (optional) is a type of number
  disk_size_gb = null
  # image_reference_id - (optional) is a type of string
  image_reference_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # os_type - (optional) is a type of string
  os_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_resource_id - (optional) is a type of string
  source_resource_id = null
  # source_uri - (optional) is a type of string
  source_uri = null
  # storage_account_id - (optional) is a type of string
  storage_account_id = null
  # storage_account_type - (required) is a type of string
  storage_account_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

  encryption_settings = [{
    disk_encryption_key = [{
      secret_url      = null
      source_vault_id = null
    }]
    enabled = null
    key_encryption_key = [{
      key_url         = null
      source_vault_id = null
    }]
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
variable "create_option" {
  description = "(required)"
  type        = string
}

variable "disk_encryption_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_iops_read_write" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disk_mbps_read_write" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disk_size_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "image_reference_id" {
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

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source_resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_type" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "encryption_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disk_encryption_key = list(object(
        {
          secret_url      = string
          source_vault_id = string
        }
      ))
      enabled = bool
      key_encryption_key = list(object(
        {
          key_url         = string
          source_vault_id = string
        }
      ))
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
resource "azurerm_managed_disk" "this" {
  create_option          = var.create_option
  disk_encryption_set_id = var.disk_encryption_set_id
  disk_iops_read_write   = var.disk_iops_read_write
  disk_mbps_read_write   = var.disk_mbps_read_write
  disk_size_gb           = var.disk_size_gb
  image_reference_id     = var.image_reference_id
  location               = var.location
  name                   = var.name
  os_type                = var.os_type
  resource_group_name    = var.resource_group_name
  source_resource_id     = var.source_resource_id
  source_uri             = var.source_uri
  storage_account_id     = var.storage_account_id
  storage_account_type   = var.storage_account_type
  tags                   = var.tags
  zones                  = var.zones

  dynamic "encryption_settings" {
    for_each = var.encryption_settings
    content {
      enabled = encryption_settings.value["enabled"]

      dynamic "disk_encryption_key" {
        for_each = encryption_settings.value.disk_encryption_key
        content {
          secret_url      = disk_encryption_key.value["secret_url"]
          source_vault_id = disk_encryption_key.value["source_vault_id"]
        }
      }

      dynamic "key_encryption_key" {
        for_each = encryption_settings.value.key_encryption_key
        content {
          key_url         = key_encryption_key.value["key_url"]
          source_vault_id = key_encryption_key.value["source_vault_id"]
        }
      }

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
output "disk_iops_read_write" {
  description = "returns a number"
  value       = azurerm_managed_disk.this.disk_iops_read_write
}

output "disk_mbps_read_write" {
  description = "returns a number"
  value       = azurerm_managed_disk.this.disk_mbps_read_write
}

output "disk_size_gb" {
  description = "returns a number"
  value       = azurerm_managed_disk.this.disk_size_gb
}

output "id" {
  description = "returns a string"
  value       = azurerm_managed_disk.this.id
}

output "source_uri" {
  description = "returns a string"
  value       = azurerm_managed_disk.this.source_uri
}

output "this" {
  value = azurerm_managed_disk.this
}
```

[top](#index)