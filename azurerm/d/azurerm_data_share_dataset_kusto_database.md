# azurerm_data_share_dataset_kusto_database

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
module "azurerm_data_share_dataset_kusto_database" {
  source = "./modules/azurerm/d/azurerm_data_share_dataset_kusto_database"

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
data "azurerm_data_share_dataset_kusto_database" "this" {
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
  value       = data.azurerm_data_share_dataset_kusto_database.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_kusto_database.this.id
}

output "kusto_cluster_location" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_kusto_database.this.kusto_cluster_location
}

output "kusto_database_id" {
  description = "returns a string"
  value       = data.azurerm_data_share_dataset_kusto_database.this.kusto_database_id
}

output "this" {
  value = azurerm_data_share_dataset_kusto_database.this
}
```

[top](#index)