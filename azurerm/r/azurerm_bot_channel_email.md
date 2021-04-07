# azurerm_bot_channel_email

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
module "azurerm_bot_channel_email" {
  source = "./modules/azurerm/r/azurerm_bot_channel_email"

  # bot_name - (required) is a type of string
  bot_name = null
  # email_address - (required) is a type of string
  email_address = null
  # email_password - (required) is a type of string
  email_password = null
  # location - (required) is a type of string
  location = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "bot_name" {
  description = "(required)"
  type        = string
}

variable "email_address" {
  description = "(required)"
  type        = string
}

variable "email_password" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
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
resource "azurerm_bot_channel_email" "this" {
  # bot_name - (required) is a type of string
  bot_name = var.bot_name
  # email_address - (required) is a type of string
  email_address = var.email_address
  # email_password - (required) is a type of string
  email_password = var.email_password
  # location - (required) is a type of string
  location = var.location
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
  value       = azurerm_bot_channel_email.this.id
}

output "this" {
  value = azurerm_bot_channel_email.this
}
```

[top](#index)