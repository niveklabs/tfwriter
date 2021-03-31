# azurerm_data_share_dataset_data_lake_gen1

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
module "azurerm_data_share_dataset_data_lake_gen1" {
  source = "./modules/azurerm/r/azurerm_data_share_dataset_data_lake_gen1"

  # data_lake_store_id - (required) is a type of string
  data_lake_store_id = null
  # data_share_id - (required) is a type of string
  data_share_id = null
  # file_name - (optional) is a type of string
  file_name = null
  # folder_path - (required) is a type of string
  folder_path = null
  # name - (required) is a type of string
  name = null

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
variable "data_lake_store_id" {
  description = "(required)"
  type        = string
}

variable "data_share_id" {
  description = "(required)"
  type        = string
}

variable "file_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "folder_path" {
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
resource "azurerm_data_share_dataset_data_lake_gen1" "this" {
  data_lake_store_id = var.data_lake_store_id
  data_share_id      = var.data_share_id
  file_name          = var.file_name
  folder_path        = var.folder_path
  name               = var.name

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
  value       = azurerm_data_share_dataset_data_lake_gen1.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_data_share_dataset_data_lake_gen1.this.id
}

output "this" {
  value = azurerm_data_share_dataset_data_lake_gen1.this
}
```

[top](#index)