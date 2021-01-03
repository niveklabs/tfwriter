# azurerm_cosmosdb_sql_stored_procedure

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
module "azurerm_cosmosdb_sql_stored_procedure" {
  source = "./modules/azurerm/r/azurerm_cosmosdb_sql_stored_procedure"

  # account_name - (required) is a type of string
  account_name = null
  # body - (required) is a type of string
  body = null
  # container_name - (required) is a type of string
  container_name = null
  # database_name - (required) is a type of string
  database_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "body" {
  description = "(required)"
  type        = string
}

variable "container_name" {
  description = "(required)"
  type        = string
}

variable "database_name" {
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
resource "azurerm_cosmosdb_sql_stored_procedure" "this" {
  account_name        = var.account_name
  body                = var.body
  container_name      = var.container_name
  database_name       = var.database_name
  name                = var.name
  resource_group_name = var.resource_group_name

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
  value       = azurerm_cosmosdb_sql_stored_procedure.this.id
}

output "this" {
  value = azurerm_cosmosdb_sql_stored_procedure.this
}
```

[top](#index)