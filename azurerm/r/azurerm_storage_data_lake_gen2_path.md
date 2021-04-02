# azurerm_storage_data_lake_gen2_path

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
module "azurerm_storage_data_lake_gen2_path" {
  source = "./modules/azurerm/r/azurerm_storage_data_lake_gen2_path"

  # filesystem_name - (required) is a type of string
  filesystem_name = null
  # group - (optional) is a type of string
  group = null
  # owner - (optional) is a type of string
  owner = null
  # path - (required) is a type of string
  path = null
  # resource - (required) is a type of string
  resource = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null

  ace = [{
    id          = null
    permissions = null
    scope       = null
    type        = null
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
variable "filesystem_name" {
  description = "(required)"
  type        = string
}

variable "group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "resource" {
  description = "(required)"
  type        = string
}

variable "storage_account_id" {
  description = "(required)"
  type        = string
}

variable "ace" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id          = string
      permissions = string
      scope       = string
      type        = string
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
resource "azurerm_storage_data_lake_gen2_path" "this" {
  filesystem_name    = var.filesystem_name
  group              = var.group
  owner              = var.owner
  path               = var.path
  resource           = var.resource
  storage_account_id = var.storage_account_id

  dynamic "ace" {
    for_each = var.ace
    content {
      id          = ace.value["id"]
      permissions = ace.value["permissions"]
      scope       = ace.value["scope"]
      type        = ace.value["type"]
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
output "group" {
  description = "returns a string"
  value       = azurerm_storage_data_lake_gen2_path.this.group
}

output "id" {
  description = "returns a string"
  value       = azurerm_storage_data_lake_gen2_path.this.id
}

output "owner" {
  description = "returns a string"
  value       = azurerm_storage_data_lake_gen2_path.this.owner
}

output "this" {
  value = azurerm_storage_data_lake_gen2_path.this
}
```

[top](#index)