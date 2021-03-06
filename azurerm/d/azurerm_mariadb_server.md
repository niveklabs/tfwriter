# azurerm_mariadb_server

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
module "azurerm_mariadb_server" {
  source = "./modules/azurerm/d/azurerm_mariadb_server"

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
data "azurerm_mariadb_server" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
output "administrator_login" {
  description = "returns a string"
  value       = data.azurerm_mariadb_server.this.administrator_login
}

output "fqdn" {
  description = "returns a string"
  value       = data.azurerm_mariadb_server.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_mariadb_server.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_mariadb_server.this.location
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_mariadb_server.this.sku_name
}

output "ssl_enforcement" {
  description = "returns a string"
  value       = data.azurerm_mariadb_server.this.ssl_enforcement
}

output "storage_profile" {
  description = "returns a list of object"
  value       = data.azurerm_mariadb_server.this.storage_profile
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_mariadb_server.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_mariadb_server.this.version
}

output "this" {
  value = azurerm_mariadb_server.this
}
```

[top](#index)