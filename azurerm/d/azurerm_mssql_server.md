# azurerm_mssql_server

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
module "azurerm_mssql_server" {
  source = "./modules/azurerm/d/azurerm_mssql_server"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
data "azurerm_mssql_server" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "administrator_login" {
  description = "returns a string"
  value       = data.azurerm_mssql_server.this.administrator_login
}

output "fully_qualified_domain_name" {
  description = "returns a string"
  value       = data.azurerm_mssql_server.this.fully_qualified_domain_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_mssql_server.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_mssql_server.this.identity
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_mssql_server.this.location
}

output "restorable_dropped_database_ids" {
  description = "returns a list of string"
  value       = data.azurerm_mssql_server.this.restorable_dropped_database_ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_mssql_server.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_mssql_server.this.version
}

output "this" {
  value = azurerm_mssql_server.this
}
```

[top](#index)