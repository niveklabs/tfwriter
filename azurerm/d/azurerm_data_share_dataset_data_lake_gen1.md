# azurerm_data_share_dataset_data_lake_gen1

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
module "azurerm_data_share_dataset_data_lake_gen1" {
  source = "./modules/azurerm/d/azurerm_data_share_dataset_data_lake_gen1"

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
data "azurerm_data_share_dataset_data_lake_gen1" "this" {
  # data_share_id - (required) is a type of string
  data_share_id = var.data_share_id
  # name - (required) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "data_lake_store_id" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen1.this.data_lake_store_id
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen1.this.display_name
}

output "file_name" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen1.this.file_name
}

output "folder_path" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen1.this.folder_path
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_data_lake_gen1.this.id
}

output "this" {
  value = azurerm_data_share_dataset_data_lake_gen1.this
}
```

[top](#index)