# azurerm_bot_channel_slack

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
module "azurerm_bot_channel_slack" {
  source = "./modules/azurerm/r/azurerm_bot_channel_slack"

  # bot_name - (required) is a type of string
  bot_name = null
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # landing_page_url - (optional) is a type of string
  landing_page_url = null
  # location - (required) is a type of string
  location = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # verification_token - (required) is a type of string
  verification_token = null

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

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
  description = "(required)"
  type        = string
}

variable "landing_page_url" {
  description = "(optional)"
  type        = string
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

variable "verification_token" {
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
resource "azurerm_bot_channel_slack" "this" {
  bot_name            = var.bot_name
  client_id           = var.client_id
  client_secret       = var.client_secret
  landing_page_url    = var.landing_page_url
  location            = var.location
  resource_group_name = var.resource_group_name
  verification_token  = var.verification_token

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
  value       = azurerm_bot_channel_slack.this.id
}

output "this" {
  value = azurerm_bot_channel_slack.this
}
```

[top](#index)