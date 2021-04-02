# azurerm_api_management_group_user

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
module "azurerm_api_management_group_user" {
  source = "./modules/azurerm/r/azurerm_api_management_group_user"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # group_name - (required) is a type of string
  group_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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

variable "group_name" {
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
resource "azurerm_api_management_group_user" "this" {
  api_management_name = var.api_management_name
  group_name          = var.group_name
  resource_group_name = var.resource_group_name
  user_id             = var.user_id

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
  value       = azurerm_api_management_group_user.this.id
}

output "this" {
  value = azurerm_api_management_group_user.this
}
```

[top](#index)