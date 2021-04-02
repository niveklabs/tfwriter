# azurerm_blueprint_assignment

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
module "azurerm_blueprint_assignment" {
  source = "./modules/azurerm/r/azurerm_blueprint_assignment"

  # location - (required) is a type of string
  location = null
  # lock_exclude_principals - (optional) is a type of list of string
  lock_exclude_principals = []
  # lock_mode - (optional) is a type of string
  lock_mode = null
  # name - (required) is a type of string
  name = null
  # parameter_values - (optional) is a type of string
  parameter_values = null
  # resource_groups - (optional) is a type of string
  resource_groups = null
  # target_subscription_id - (required) is a type of string
  target_subscription_id = null
  # version_id - (required) is a type of string
  version_id = null

  identity = [{
    identity_ids = []
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "lock_exclude_principals" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "lock_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameter_values" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_subscription_id" {
  description = "(required)"
  type        = string
}

variable "version_id" {
  description = "(required)"
  type        = string
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_ids = list(string)
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
resource "azurerm_blueprint_assignment" "this" {
  location                = var.location
  lock_exclude_principals = var.lock_exclude_principals
  lock_mode               = var.lock_mode
  name                    = var.name
  parameter_values        = var.parameter_values
  resource_groups         = var.resource_groups
  target_subscription_id  = var.target_subscription_id
  version_id              = var.version_id

  dynamic "identity" {
    for_each = var.identity
    content {
      identity_ids = identity.value["identity_ids"]
      type         = identity.value["type"]
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
output "blueprint_name" {
  description = "returns a string"
  value       = azurerm_blueprint_assignment.this.blueprint_name
}

output "description" {
  description = "returns a string"
  value       = azurerm_blueprint_assignment.this.description
}

output "display_name" {
  description = "returns a string"
  value       = azurerm_blueprint_assignment.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_blueprint_assignment.this.id
}

output "type" {
  description = "returns a string"
  value       = azurerm_blueprint_assignment.this.type
}

output "this" {
  value = azurerm_blueprint_assignment.this
}
```

[top](#index)