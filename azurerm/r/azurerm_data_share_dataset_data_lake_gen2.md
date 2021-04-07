# azurerm_data_share_dataset_data_lake_gen2

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_data_share_dataset_data_lake_gen2" {
  source = "./modules/azurerm/r/azurerm_data_share_dataset_data_lake_gen2"

  # file_path - (optional) is a type of string
  file_path = null
  # file_system_name - (required) is a type of string
  file_system_name = null
  # folder_path - (optional) is a type of string
  folder_path = null
  # name - (required) is a type of string
  name = null
  # share_id - (required) is a type of string
  share_id = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null

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
variable "file_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_system_name" {
  description = "(required)"
  type        = string
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

variable "share_id" {
  description = "(required)"
  type        = string
}

variable "storage_account_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_data_share_dataset_data_lake_gen2" "this" {
  # file_path - (optional) is a type of string
  file_path = var.file_path
  # file_system_name - (required) is a type of string
  file_system_name = var.file_system_name
  # folder_path - (optional) is a type of string
  folder_path = var.folder_path
  # name - (required) is a type of string
  name = var.name
  # share_id - (required) is a type of string
  share_id = var.share_id
  # storage_account_id - (required) is a type of string
  storage_account_id = var.storage_account_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = azurerm_data_share_dataset_data_lake_gen2.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_data_share_dataset_data_lake_gen2.this.id
}

output "this" {
  value = azurerm_data_share_dataset_data_lake_gen2.this
}
```

[top](#index)