# azurerm_kusto_database_principal

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_kusto_database_principal" {
  source = "./modules/azurerm/r/azurerm_kusto_database_principal"

  # client_id - (required) is a type of string
  client_id = null
  # cluster_name - (required) is a type of string
  cluster_name = null
  # database_name - (required) is a type of string
  database_name = null
  # object_id - (required) is a type of string
  object_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # role - (required) is a type of string
  role = null
  # type - (required) is a type of string
  type = null

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
variable "client_id" {
  description = "(required)"
  type        = string
}

variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "object_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "type" {
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
resource "azurerm_kusto_database_principal" "this" {
  client_id           = var.client_id
  cluster_name        = var.cluster_name
  database_name       = var.database_name
  object_id           = var.object_id
  resource_group_name = var.resource_group_name
  role                = var.role
  type                = var.type

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
output "app_id" {
  description = "returns a string"
  value       = azurerm_kusto_database_principal.this.app_id
}

output "email" {
  description = "returns a string"
  value       = azurerm_kusto_database_principal.this.email
}

output "fully_qualified_name" {
  description = "returns a string"
  value       = azurerm_kusto_database_principal.this.fully_qualified_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_kusto_database_principal.this.id
}

output "name" {
  description = "returns a string"
  value       = azurerm_kusto_database_principal.this.name
}

output "this" {
  value = azurerm_kusto_database_principal.this
}
```

[top](#index)