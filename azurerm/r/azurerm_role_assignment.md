# azurerm_role_assignment

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_role_assignment" {
  source = "./modules/azurerm/r/azurerm_role_assignment"

  # name - (optional) is a type of string
  name = null
  # principal_id - (required) is a type of string
  principal_id = null
  # role_definition_id - (optional) is a type of string
  role_definition_id = null
  # role_definition_name - (optional) is a type of string
  role_definition_name = null
  # scope - (required) is a type of string
  scope = null
  # skip_service_principal_aad_check - (optional) is a type of bool
  skip_service_principal_aad_check = null

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
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "principal_id" {
  description = "(required)"
  type        = string
}

variable "role_definition_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_definition_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "skip_service_principal_aad_check" {
  description = "(optional)"
  type        = bool
  default     = null
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
resource "azurerm_role_assignment" "this" {
  name                             = var.name
  principal_id                     = var.principal_id
  role_definition_id               = var.role_definition_id
  role_definition_name             = var.role_definition_name
  scope                            = var.scope
  skip_service_principal_aad_check = var.skip_service_principal_aad_check

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
  value       = azurerm_role_assignment.this.id
}

output "name" {
  description = "returns a string"
  value       = azurerm_role_assignment.this.name
}

output "principal_type" {
  description = "returns a string"
  value       = azurerm_role_assignment.this.principal_type
}

output "role_definition_id" {
  description = "returns a string"
  value       = azurerm_role_assignment.this.role_definition_id
}

output "role_definition_name" {
  description = "returns a string"
  value       = azurerm_role_assignment.this.role_definition_name
}

output "skip_service_principal_aad_check" {
  description = "returns a bool"
  value       = azurerm_role_assignment.this.skip_service_principal_aad_check
}

output "this" {
  value = azurerm_role_assignment.this
}
```

[top](#index)