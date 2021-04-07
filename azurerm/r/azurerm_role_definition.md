# azurerm_role_definition

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_role_definition" {
  source = "./modules/azurerm/r/azurerm_role_definition"

  # assignable_scopes - (optional) is a type of list of string
  assignable_scopes = []
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # role_definition_id - (optional) is a type of string
  role_definition_id = null
  # scope - (required) is a type of string
  scope = null

  permissions = [{
    actions          = []
    data_actions     = []
    not_actions      = []
    not_data_actions = []
  }]

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
variable "assignable_scopes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role_definition_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      actions          = list(string)
      data_actions     = set(string)
      not_actions      = list(string)
      not_data_actions = set(string)
    }
  ))
  default = []
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
resource "azurerm_role_definition" "this" {
  # assignable_scopes - (optional) is a type of list of string
  assignable_scopes = var.assignable_scopes
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # role_definition_id - (optional) is a type of string
  role_definition_id = var.role_definition_id
  # scope - (required) is a type of string
  scope = var.scope

  dynamic "permissions" {
    for_each = var.permissions
    content {
      # actions - (optional) is a type of list of string
      actions = permissions.value["actions"]
      # data_actions - (optional) is a type of set of string
      data_actions = permissions.value["data_actions"]
      # not_actions - (optional) is a type of list of string
      not_actions = permissions.value["not_actions"]
      # not_data_actions - (optional) is a type of set of string
      not_data_actions = permissions.value["not_data_actions"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "assignable_scopes" {
  description = "returns a list of string"
  value       = azurerm_role_definition.this.assignable_scopes
}

output "id" {
  description = "returns a string"
  value       = azurerm_role_definition.this.id
}

output "role_definition_id" {
  description = "returns a string"
  value       = azurerm_role_definition.this.role_definition_id
}

output "role_definition_resource_id" {
  description = "returns a string"
  value       = azurerm_role_definition.this.role_definition_resource_id
}

output "this" {
  value = azurerm_role_definition.this
}
```

[top](#index)