# azurerm_database_migration_project

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_database_migration_project" {
  source = "./modules/azurerm/d/azurerm_database_migration_project"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_name - (required) is a type of string
  service_name = null

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

variable "service_name" {
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
data "azurerm_database_migration_project" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  service_name        = var.service_name

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_database_migration_project.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_database_migration_project.this.location
}

output "source_platform" {
  description = "returns a string"
  value       = data.azurerm_database_migration_project.this.source_platform
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_database_migration_project.this.tags
}

output "target_platform" {
  description = "returns a string"
  value       = data.azurerm_database_migration_project.this.target_platform
}

output "this" {
  value = azurerm_database_migration_project.this
}
```

[top](#index)