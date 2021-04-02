# azurerm_data_share_dataset_blob_storage

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
module "azurerm_data_share_dataset_blob_storage" {
  source = "./modules/azurerm/d/azurerm_data_share_dataset_blob_storage"

  # data_share_id - (required) is a type of string
  data_share_id = null
  # name - (required) is a type of string
  name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data_share_id" {
  description = "(required)"
  type        = string
}

variable "name" {
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
data "azurerm_data_share_dataset_blob_storage" "this" {
  data_share_id = var.data_share_id
  name          = var.name

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
output "container_name" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_blob_storage.this.container_name
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_blob_storage.this.display_name
}

output "file_path" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_blob_storage.this.file_path
}

output "folder_path" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_blob_storage.this.folder_path
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_blob_storage.this.id
}

output "storage_account" {
  description = "returns a list of object"
  value       = data.azurerm_data_share_dataset_blob_storage.this.storage_account
}

output "this" {
  value = azurerm_data_share_dataset_blob_storage.this
}
```

[top](#index)