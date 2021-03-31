# azurerm_bot_connection

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_bot_connection" {
  source = "./modules/azurerm/r/azurerm_bot_connection"

  # bot_name - (required) is a type of string
  bot_name = null
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scopes - (optional) is a type of string
  scopes = null
  # service_provider_name - (required) is a type of string
  service_provider_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "scopes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_provider_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "azurerm_bot_connection" "this" {
  bot_name              = var.bot_name
  client_id             = var.client_id
  client_secret         = var.client_secret
  location              = var.location
  name                  = var.name
  parameters            = var.parameters
  resource_group_name   = var.resource_group_name
  scopes                = var.scopes
  service_provider_name = var.service_provider_name
  tags                  = var.tags

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
  value       = azurerm_bot_connection.this.id
}

output "this" {
  value = azurerm_bot_connection.this
}
```

[top](#index)