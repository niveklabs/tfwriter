# azurerm_machine_learning_workspace

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
module "azurerm_machine_learning_workspace" {
  source = "./modules/azurerm/r/azurerm_machine_learning_workspace"

  # application_insights_id - (required) is a type of string
  application_insights_id = null
  # container_registry_id - (optional) is a type of string
  container_registry_id = null
  # description - (optional) is a type of string
  description = null
  # friendly_name - (optional) is a type of string
  friendly_name = null
  # high_business_impact - (optional) is a type of bool
  high_business_impact = null
  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (optional) is a type of string
  sku_name = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
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
variable "application_insights_id" {
  description = "(required)"
  type        = string
}

variable "container_registry_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "friendly_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "high_business_impact" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_vault_id" {
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "identity" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
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
resource "azurerm_machine_learning_workspace" "this" {
  application_insights_id = var.application_insights_id
  container_registry_id   = var.container_registry_id
  description             = var.description
  friendly_name           = var.friendly_name
  high_business_impact    = var.high_business_impact
  key_vault_id            = var.key_vault_id
  location                = var.location
  name                    = var.name
  resource_group_name     = var.resource_group_name
  sku_name                = var.sku_name
  storage_account_id      = var.storage_account_id
  tags                    = var.tags

  dynamic "identity" {
    for_each = var.identity
    content {
      type = identity.value["type"]
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
  value       = azurerm_machine_learning_workspace.this.id
}

output "this" {
  value = azurerm_machine_learning_workspace.this
}
```

[top](#index)