# azurerm_mssql_elasticpool

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
module "azurerm_mssql_elasticpool" {
  source = "./modules/azurerm/d/azurerm_mssql_elasticpool"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # server_name - (required) is a type of string
  server_name = null

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
data "azurerm_mssql_elasticpool" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # server_name - (required) is a type of string
  server_name = var.server_name

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_mssql_elasticpool.this.id
}

output "license_type" {
  description = "returns a string"
  value       = data.azurerm_mssql_elasticpool.this.license_type
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_mssql_elasticpool.this.location
}

output "max_size_bytes" {
  description = "returns a number"
  value       = data.azurerm_mssql_elasticpool.this.max_size_bytes
}

output "max_size_gb" {
  description = "returns a number"
  value       = data.azurerm_mssql_elasticpool.this.max_size_gb
}

output "per_db_max_capacity" {
  description = "returns a number"
  value       = data.azurerm_mssql_elasticpool.this.per_db_max_capacity
}

output "per_db_min_capacity" {
  description = "returns a number"
  value       = data.azurerm_mssql_elasticpool.this.per_db_min_capacity
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_mssql_elasticpool.this.tags
}

output "zone_redundant" {
  description = "returns a bool"
  value       = data.azurerm_mssql_elasticpool.this.zone_redundant
}

output "this" {
  value = azurerm_mssql_elasticpool.this
}
```

[top](#index)