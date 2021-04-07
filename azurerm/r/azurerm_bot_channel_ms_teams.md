# azurerm_bot_channel_ms_teams

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
module "azurerm_bot_channel_ms_teams" {
  source = "./modules/azurerm/r/azurerm_bot_channel_ms_teams"

  # bot_name - (required) is a type of string
  bot_name = null
  # calling_web_hook - (optional) is a type of string
  calling_web_hook = null
  # enable_calling - (optional) is a type of bool
  enable_calling = null
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

variable "calling_web_hook" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_calling" {
  description = "(optional)"
  type        = bool
  default     = null
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
resource "azurerm_bot_channel_ms_teams" "this" {
  # bot_name - (required) is a type of string
  bot_name = var.bot_name
  # calling_web_hook - (optional) is a type of string
  calling_web_hook = var.calling_web_hook
  # enable_calling - (optional) is a type of bool
  enable_calling = var.enable_calling
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
output "calling_web_hook" {
  description = "returns a string"
  value       = azurerm_bot_channel_ms_teams.this.calling_web_hook
}

output "id" {
  description = "returns a string"
  value       = azurerm_bot_channel_ms_teams.this.id
}

output "this" {
  value = azurerm_bot_channel_ms_teams.this
}
```

[top](#index)