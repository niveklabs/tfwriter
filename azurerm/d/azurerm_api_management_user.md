# azurerm_api_management_user

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
module "azurerm_api_management_user" {
  source = "./modules/azurerm/d/azurerm_api_management_user"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # user_id - (required) is a type of string
  user_id = null

  timeouts = [{
    read = null
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "user_id" {
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
data "azurerm_api_management_user" "this" {
  api_management_name = var.api_management_name
  resource_group_name = var.resource_group_name
  user_id             = var.user_id

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
output "email" {
  description = "returns a string"
  value       = data.azurerm_api_management_user.this.email
}

output "first_name" {
  description = "returns a string"
  value       = data.azurerm_api_management_user.this.first_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_api_management_user.this.id
}

output "last_name" {
  description = "returns a string"
  value       = data.azurerm_api_management_user.this.last_name
}

output "note" {
  description = "returns a string"
  value       = data.azurerm_api_management_user.this.note
}

output "state" {
  description = "returns a string"
  value       = data.azurerm_api_management_user.this.state
}

output "this" {
  value = azurerm_api_management_user.this
}
```

[top](#index)