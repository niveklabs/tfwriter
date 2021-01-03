# azurerm_automation_credential

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
module "azurerm_automation_credential" {
  source = "./modules/azurerm/r/azurerm_automation_credential"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # username - (required) is a type of string
  username = null

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
variable "automation_account_name" {
  description = "(required)"
  type        = string
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

variable "password" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "username" {
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
resource "azurerm_automation_credential" "this" {
  automation_account_name = var.automation_account_name
  description             = var.description
  name                    = var.name
  password                = var.password
  resource_group_name     = var.resource_group_name
  username                = var.username

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
  value       = azurerm_automation_credential.this.id
}

output "this" {
  value = azurerm_automation_credential.this
}
```

[top](#index)