# azurerm_bot_channel_directline

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
module "azurerm_bot_channel_directline" {
  source = "./modules/azurerm/r/azurerm_bot_channel_directline"

  # bot_name - (required) is a type of string
  bot_name = null
  # location - (required) is a type of string
  location = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  site = [{
    enabled                         = null
    enhanced_authentication_enabled = null
    id                              = null
    key                             = null
    key2                            = null
    name                            = null
    trusted_origins                 = []
    v1_allowed                      = null
    v3_allowed                      = null
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
variable "bot_name" {
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

variable "site" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      enabled                         = bool
      enhanced_authentication_enabled = bool
      id                              = string
      key                             = string
      key2                            = string
      name                            = string
      trusted_origins                 = set(string)
      v1_allowed                      = bool
      v3_allowed                      = bool
    }
  ))
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
resource "azurerm_bot_channel_directline" "this" {
  bot_name            = var.bot_name
  location            = var.location
  resource_group_name = var.resource_group_name

  dynamic "site" {
    for_each = var.site
    content {
      enabled                         = site.value["enabled"]
      enhanced_authentication_enabled = site.value["enhanced_authentication_enabled"]
      name                            = site.value["name"]
      trusted_origins                 = site.value["trusted_origins"]
      v1_allowed                      = site.value["v1_allowed"]
      v3_allowed                      = site.value["v3_allowed"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_bot_channel_directline.this.id
}

output "this" {
  value = azurerm_bot_channel_directline.this
}
```

[top](#index)