# azurerm_notification_hub

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
module "azurerm_notification_hub" {
  source = "./modules/azurerm/r/azurerm_notification_hub"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  apns_credential = [{
    application_mode = null
    bundle_id        = null
    key_id           = null
    team_id          = null
    token            = null
  }]

  gcm_credential = [{
    api_key = null
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "apns_credential" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      application_mode = string
      bundle_id        = string
      key_id           = string
      team_id          = string
      token            = string
    }
  ))
  default = []
}

variable "gcm_credential" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      api_key = string
    }
  ))
  default = []
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
resource "azurerm_notification_hub" "this" {
  location            = var.location
  name                = var.name
  namespace_name      = var.namespace_name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "apns_credential" {
    for_each = var.apns_credential
    content {
      application_mode = apns_credential.value["application_mode"]
      bundle_id        = apns_credential.value["bundle_id"]
      key_id           = apns_credential.value["key_id"]
      team_id          = apns_credential.value["team_id"]
      token            = apns_credential.value["token"]
    }
  }

  dynamic "gcm_credential" {
    for_each = var.gcm_credential
    content {
      api_key = gcm_credential.value["api_key"]
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
  value       = azurerm_notification_hub.this.id
}

output "this" {
  value = azurerm_notification_hub.this
}
```

[top](#index)