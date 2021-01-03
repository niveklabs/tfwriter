# azurerm_data_share_dataset_blob_storage

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
module "azurerm_data_share_dataset_blob_storage" {
  source = "./modules/azurerm/r/azurerm_data_share_dataset_blob_storage"

  # container_name - (required) is a type of string
  container_name = null
  # data_share_id - (required) is a type of string
  data_share_id = null
  # file_path - (optional) is a type of string
  file_path = null
  # folder_path - (optional) is a type of string
  folder_path = null
  # name - (required) is a type of string
  name = null

  storage_account = [{
    name                = null
    resource_group_name = null
    subscription_id     = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "container_name" {
  description = "(required)"
  type        = string
}

variable "data_share_id" {
  description = "(required)"
  type        = string
}

variable "file_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "folder_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "storage_account" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      name                = string
      resource_group_name = string
      subscription_id     = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_data_share_dataset_blob_storage" "this" {
  container_name = var.container_name
  data_share_id  = var.data_share_id
  file_path      = var.file_path
  folder_path    = var.folder_path
  name           = var.name

  dynamic "storage_account" {
    for_each = var.storage_account
    content {
      name                = storage_account.value["name"]
      resource_group_name = storage_account.value["resource_group_name"]
      subscription_id     = storage_account.value["subscription_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = azurerm_data_share_dataset_blob_storage.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_data_share_dataset_blob_storage.this.id
}

output "this" {
  value = azurerm_data_share_dataset_blob_storage.this
}
```

[top](#index)