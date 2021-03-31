# azurerm_policy_assignment

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
module "azurerm_policy_assignment" {
  source = "./modules/azurerm/r/azurerm_policy_assignment"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # enforcement_mode - (optional) is a type of bool
  enforcement_mode = null
  # location - (optional) is a type of string
  location = null
  # metadata - (optional) is a type of string
  metadata = null
  # name - (required) is a type of string
  name = null
  # not_scopes - (optional) is a type of list of string
  not_scopes = []
  # parameters - (optional) is a type of string
  parameters = null
  # policy_definition_id - (required) is a type of string
  policy_definition_id = null
  # scope - (required) is a type of string
  scope = null

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
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

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enforcement_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "not_scopes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "parameters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_definition_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
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
resource "azurerm_policy_assignment" "this" {
  description          = var.description
  display_name         = var.display_name
  enforcement_mode     = var.enforcement_mode
  location             = var.location
  metadata             = var.metadata
  name                 = var.name
  not_scopes           = var.not_scopes
  parameters           = var.parameters
  policy_definition_id = var.policy_definition_id
  scope                = var.scope

  dynamic "identity" {
    for_each = var.identity
    content {
      type = identity.value["type"]
    }
  }

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
output "id" {
  description = "returns a string"
  value       = azurerm_policy_assignment.this.id
}

output "metadata" {
  description = "returns a string"
  value       = azurerm_policy_assignment.this.metadata
}

output "this" {
  value = azurerm_policy_assignment.this
}
```

[top](#index)