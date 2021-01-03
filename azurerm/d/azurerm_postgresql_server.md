# azurerm_postgresql_server

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
module "azurerm_postgresql_server" {
  source = "./modules/azurerm/d/azurerm_postgresql_server"

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
data "azurerm_postgresql_server" "this" {
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
  value       = data.azurerm_postgresql_server.this.administrator_login
}

output "fqdn" {
  description = "returns a string"
  value       = data.azurerm_postgresql_server.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_postgresql_server.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_postgresql_server.this.identity
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_postgresql_server.this.location
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_postgresql_server.this.sku_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_postgresql_server.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_postgresql_server.this.version
}

output "this" {
  value = azurerm_postgresql_server.this
}
```

[top](#index)