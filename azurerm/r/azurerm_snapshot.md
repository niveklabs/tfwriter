# azurerm_snapshot

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
module "azurerm_snapshot" {
  source = "./modules/azurerm/r/azurerm_snapshot"

  # create_option - (required) is a type of string
  create_option = null
  # disk_size_gb - (optional) is a type of number
  disk_size_gb = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_resource_id - (optional) is a type of string
  source_resource_id = null
  # source_uri - (optional) is a type of string
  source_uri = null
  # storage_account_id - (optional) is a type of string
  storage_account_id = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "disk_size_gb" {
  description = "(optional)"
  type        = number
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "azurerm_snapshot" "this" {
  create_option       = var.create_option
  disk_size_gb        = var.disk_size_gb
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  source_resource_id  = var.source_resource_id
  source_uri          = var.source_uri
  storage_account_id  = var.storage_account_id
  tags                = var.tags

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
output "disk_size_gb" {
  description = "returns a number"
  value       = azurerm_snapshot.this.disk_size_gb
}

output "id" {
  description = "returns a string"
  value       = azurerm_snapshot.this.id
}

output "this" {
  value = azurerm_snapshot.this
}
```

[top](#index)