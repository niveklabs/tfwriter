# azurerm_data_share_dataset_kusto_database

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
module "azurerm_data_share_dataset_kusto_database" {
  source = "./modules/azurerm/r/azurerm_data_share_dataset_kusto_database"

  # kusto_database_id - (required) is a type of string
  kusto_database_id = null
  # name - (required) is a type of string
  name = null
  # share_id - (required) is a type of string
  share_id = null

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
variable "kusto_database_id" {
  description = "(required)"
  type        = string
}

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
resource "azurerm_data_share_dataset_kusto_database" "this" {
  # kusto_database_id - (required) is a type of string
  kusto_database_id = var.kusto_database_id
  # name - (required) is a type of string
  name = var.name
  # share_id - (required) is a type of string
  share_id = var.share_id

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
  value       = azurerm_data_share_dataset_kusto_database.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_data_share_dataset_kusto_database.this.id
}

output "kusto_cluster_location" {
  description = "returns a string"
  value       = azurerm_data_share_dataset_kusto_database.this.kusto_cluster_location
}

output "this" {
  value = azurerm_data_share_dataset_kusto_database.this
}
```

[top](#index)