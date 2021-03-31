# azurerm_blueprint_definition

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
module "azurerm_blueprint_definition" {
  source = "./modules/azurerm/d/azurerm_blueprint_definition"

  # name - (required) is a type of string
  name = null
  # scope_id - (required) is a type of string
  scope_id = null

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

variable "scope_id" {
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
data "azurerm_blueprint_definition" "this" {
  name     = var.name
  scope_id = var.scope_id

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
output "description" {
  description = "returns a string"
  value       = data.azurerm_blueprint_definition.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_blueprint_definition.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_blueprint_definition.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = data.azurerm_blueprint_definition.this.last_modified
}

output "target_scope" {
  description = "returns a string"
  value       = data.azurerm_blueprint_definition.this.target_scope
}

output "time_created" {
  description = "returns a string"
  value       = data.azurerm_blueprint_definition.this.time_created
}

output "versions" {
  description = "returns a list of string"
  value       = data.azurerm_blueprint_definition.this.versions
}

output "this" {
  value = azurerm_blueprint_definition.this
}
```

[top](#index)