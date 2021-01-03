# azurerm_mssql_database

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_mssql_database" {
  source = "./modules/azurerm/d/azurerm_mssql_database"

  # name - (required) is a type of string
  name = null
  # server_id - (required) is a type of string
  server_id = null

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

variable "server_id" {
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
data "azurerm_mssql_database" "this" {
  name      = var.name
  server_id = var.server_id

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
output "collation" {
  description = "returns a string"
  value       = data.azurerm_mssql_database.this.collation
}

output "elastic_pool_id" {
  description = "returns a string"
  value       = data.azurerm_mssql_database.this.elastic_pool_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_mssql_database.this.id
}

output "license_type" {
  description = "returns a string"
  value       = data.azurerm_mssql_database.this.license_type
}

output "max_size_gb" {
  description = "returns a number"
  value       = data.azurerm_mssql_database.this.max_size_gb
}

output "read_replica_count" {
  description = "returns a number"
  value       = data.azurerm_mssql_database.this.read_replica_count
}

output "read_scale" {
  description = "returns a bool"
  value       = data.azurerm_mssql_database.this.read_scale
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_mssql_database.this.sku_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_mssql_database.this.tags
}

output "zone_redundant" {
  description = "returns a bool"
  value       = data.azurerm_mssql_database.this.zone_redundant
}

output "this" {
  value = azurerm_mssql_database.this
}
```

[top](#index)