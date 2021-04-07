# azurerm_sql_database

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
module "azurerm_sql_database" {
  source = "./modules/azurerm/d/azurerm_sql_database"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # server_name - (required) is a type of string
  server_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "server_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
data "azurerm_sql_database" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # server_name - (required) is a type of string
  server_name = var.server_name
  # tags - (optional) is a type of map of string
  tags = var.tags

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
output "collation" {
  description = "returns a string"
  value       = data.azurerm_sql_database.this.collation
}

output "default_secondary_location" {
  description = "returns a string"
  value       = data.azurerm_sql_database.this.default_secondary_location
}

output "edition" {
  description = "returns a string"
  value       = data.azurerm_sql_database.this.edition
}

output "elastic_pool_name" {
  description = "returns a string"
  value       = data.azurerm_sql_database.this.elastic_pool_name
}

output "failover_group_id" {
  description = "returns a string"
  value       = data.azurerm_sql_database.this.failover_group_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_sql_database.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_sql_database.this.location
}

output "read_scale" {
  description = "returns a bool"
  value       = data.azurerm_sql_database.this.read_scale
}

output "this" {
  value = azurerm_sql_database.this
}
```

[top](#index)