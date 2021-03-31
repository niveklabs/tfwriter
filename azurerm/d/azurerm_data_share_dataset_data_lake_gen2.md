# azurerm_data_share_dataset_data_lake_gen2

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
module "azurerm_data_share_dataset_data_lake_gen2" {
  source = "./modules/azurerm/d/azurerm_data_share_dataset_data_lake_gen2"

  # name - (required) is a type of string
  name = null
  # share_id - (required) is a type of string
  share_id = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "share_id" {
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
data "azurerm_data_share_dataset_data_lake_gen2" "this" {
  name     = var.name
  share_id = var.share_id

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
output "display_name" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen2.this.display_name
}

output "file_path" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen2.this.file_path
}

output "file_system_name" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen2.this.file_system_name
}

output "folder_path" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen2.this.folder_path
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen2.this.id
}

output "storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen2.this.storage_account_id
}

output "this" {
  value = azurerm_data_share_dataset_data_lake_gen2.this
}
```

[top](#index)