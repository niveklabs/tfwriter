# azurerm_api_management_user

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
module "azurerm_api_management_user" {
  source = "./modules/azurerm/r/azurerm_api_management_user"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # confirmation - (optional) is a type of string
  confirmation = null
  # email - (required) is a type of string
  email = null
  # first_name - (required) is a type of string
  first_name = null
  # last_name - (required) is a type of string
  last_name = null
  # note - (optional) is a type of string
  note = null
  # password - (optional) is a type of string
  password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # state - (optional) is a type of string
  state = null
  # user_id - (required) is a type of string
  user_id = null

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
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "confirmation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "first_name" {
  description = "(required)"
  type        = string
}

variable "last_name" {
  description = "(required)"
  type        = string
}

variable "note" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id" {
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
resource "azurerm_api_management_user" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # confirmation - (optional) is a type of string
  confirmation = var.confirmation
  # email - (required) is a type of string
  email = var.email
  # first_name - (required) is a type of string
  first_name = var.first_name
  # last_name - (required) is a type of string
  last_name = var.last_name
  # note - (optional) is a type of string
  note = var.note
  # password - (optional) is a type of string
  password = var.password
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # state - (optional) is a type of string
  state = var.state
  # user_id - (required) is a type of string
  user_id = var.user_id

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
  value       = azurerm_api_management_user.this.id
}

output "state" {
  description = "returns a string"
  value       = azurerm_api_management_user.this.state
}

output "this" {
  value = azurerm_api_management_user.this
}
```

[top](#index)