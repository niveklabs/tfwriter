# azurerm_media_services_account

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
module "azurerm_media_services_account" {
  source = "./modules/azurerm/r/azurerm_media_services_account"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_authentication_type - (optional) is a type of string
  storage_authentication_type = null
  # tags - (optional) is a type of map of string
  tags = {}

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  storage_account = [{
    id         = null
    is_primary = null
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_authentication_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
    }
  ))
  default = []
}

variable "storage_account" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      id         = string
      is_primary = bool
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
resource "azurerm_media_services_account" "this" {
  location                    = var.location
  name                        = var.name
  resource_group_name         = var.resource_group_name
  storage_authentication_type = var.storage_authentication_type
  tags                        = var.tags

  dynamic "identity" {
    for_each = var.identity
    content {
      type = identity.value["type"]
    }
  }

  dynamic "storage_account" {
    for_each = var.storage_account
    content {
      id         = storage_account.value["id"]
      is_primary = storage_account.value["is_primary"]
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
  value       = azurerm_media_services_account.this.id
}

output "storage_authentication_type" {
  description = "returns a string"
  value       = azurerm_media_services_account.this.storage_authentication_type
}

output "this" {
  value = azurerm_media_services_account.this
}
```

[top](#index)