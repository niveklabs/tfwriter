# azurerm_lighthouse_definition

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
module "azurerm_lighthouse_definition" {
  source = "./modules/azurerm/r/azurerm_lighthouse_definition"

  # description - (optional) is a type of string
  description = null
  # lighthouse_definition_id - (optional) is a type of string
  lighthouse_definition_id = null
  # managing_tenant_id - (required) is a type of string
  managing_tenant_id = null
  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null

  authorization = [{
    principal_display_name = null
    principal_id           = null
    role_definition_id     = null
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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lighthouse_definition_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "managing_tenant_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "authorization" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      principal_display_name = string
      principal_id           = string
      role_definition_id     = string
    }
  ))
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
resource "azurerm_lighthouse_definition" "this" {
  # description - (optional) is a type of string
  description = var.description
  # lighthouse_definition_id - (optional) is a type of string
  lighthouse_definition_id = var.lighthouse_definition_id
  # managing_tenant_id - (required) is a type of string
  managing_tenant_id = var.managing_tenant_id
  # name - (required) is a type of string
  name = var.name
  # scope - (required) is a type of string
  scope = var.scope

  dynamic "authorization" {
    for_each = var.authorization
    content {
      # principal_display_name - (optional) is a type of string
      principal_display_name = authorization.value["principal_display_name"]
      # principal_id - (required) is a type of string
      principal_id = authorization.value["principal_id"]
      # role_definition_id - (required) is a type of string
      role_definition_id = authorization.value["role_definition_id"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_lighthouse_definition.this.id
}

output "lighthouse_definition_id" {
  description = "returns a string"
  value       = azurerm_lighthouse_definition.this.lighthouse_definition_id
}

output "this" {
  value = azurerm_lighthouse_definition.this
}
```

[top](#index)