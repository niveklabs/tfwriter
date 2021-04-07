# azurerm_management_lock

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
module "azurerm_management_lock" {
  source = "./modules/azurerm/r/azurerm_management_lock"

  # lock_level - (required) is a type of string
  lock_level = null
  # name - (required) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # scope - (required) is a type of string
  scope = null

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
variable "lock_level" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
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
resource "azurerm_management_lock" "this" {
  # lock_level - (required) is a type of string
  lock_level = var.lock_level
  # name - (required) is a type of string
  name = var.name
  # notes - (optional) is a type of string
  notes = var.notes
  # scope - (required) is a type of string
  scope = var.scope

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
  value       = azurerm_management_lock.this.id
}

output "this" {
  value = azurerm_management_lock.this
}
```

[top](#index)