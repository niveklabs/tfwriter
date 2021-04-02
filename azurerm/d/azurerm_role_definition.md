# azurerm_role_definition

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
module "azurerm_role_definition" {
  source = "./modules/azurerm/d/azurerm_role_definition"

  # name - (optional) is a type of string
  name = null
  # role_definition_id - (optional) is a type of string
  role_definition_id = null
  # scope - (optional) is a type of string
  scope = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_definition_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
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
data "azurerm_role_definition" "this" {
  name               = var.name
  role_definition_id = var.role_definition_id
  scope              = var.scope

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
output "assignable_scopes" {
  description = "returns a list of string"
  value       = data.azurerm_role_definition.this.assignable_scopes
}

output "description" {
  description = "returns a string"
  value       = data.azurerm_role_definition.this.description
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_role_definition.this.id
}

output "name" {
  description = "returns a string"
  value       = data.azurerm_role_definition.this.name
}

output "permissions" {
  description = "returns a list of object"
  value       = data.azurerm_role_definition.this.permissions
}

output "role_definition_id" {
  description = "returns a string"
  value       = data.azurerm_role_definition.this.role_definition_id
}

output "type" {
  description = "returns a string"
  value       = data.azurerm_role_definition.this.type
}

output "this" {
  value = azurerm_role_definition.this
}
```

[top](#index)