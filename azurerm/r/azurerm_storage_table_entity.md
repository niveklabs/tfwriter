# azurerm_storage_table_entity

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
module "azurerm_storage_table_entity" {
  source = "./modules/azurerm/r/azurerm_storage_table_entity"

  # entity - (required) is a type of map of string
  entity = {}
  # partition_key - (required) is a type of string
  partition_key = null
  # row_key - (required) is a type of string
  row_key = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null
  # table_name - (required) is a type of string
  table_name = null

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
variable "entity" {
  description = "(required)"
  type        = map(string)
}

variable "partition_key" {
  description = "(required)"
  type        = string
}

variable "row_key" {
  description = "(required)"
  type        = string
}

variable "storage_account_name" {
  description = "(required)"
  type        = string
}

variable "table_name" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_storage_table_entity" "this" {
  entity               = var.entity
  partition_key        = var.partition_key
  row_key              = var.row_key
  storage_account_name = var.storage_account_name
  table_name           = var.table_name

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
output "id" {
  description = "returns a string"
  value       = azurerm_storage_table_entity.this.id
}

output "this" {
  value = azurerm_storage_table_entity.this
}
```

[top](#index)