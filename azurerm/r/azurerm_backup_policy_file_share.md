# azurerm_backup_policy_file_share

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
module "azurerm_backup_policy_file_share" {
  source = "./modules/azurerm/r/azurerm_backup_policy_file_share"

  # name - (required) is a type of string
  name = null
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # timezone - (optional) is a type of string
  timezone = null

  backup = [{
    frequency = null
    time      = null
  }]

  retention_daily = [{
    count = null
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
variable "name" {
  description = "(required)"
  type        = string
}

variable "recovery_vault_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      frequency = string
      time      = string
    }
  ))
}

variable "retention_daily" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      count = number
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
resource "azurerm_backup_policy_file_share" "this" {
  # name - (required) is a type of string
  name = var.name
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = var.recovery_vault_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # timezone - (optional) is a type of string
  timezone = var.timezone

  dynamic "backup" {
    for_each = var.backup
    content {
      # frequency - (required) is a type of string
      frequency = backup.value["frequency"]
      # time - (required) is a type of string
      time = backup.value["time"]
    }
  }

  dynamic "retention_daily" {
    for_each = var.retention_daily
    content {
      # count - (required) is a type of number
      count = retention_daily.value["count"]
    }
  }

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
  value       = azurerm_backup_policy_file_share.this.id
}

output "this" {
  value = azurerm_backup_policy_file_share.this
}
```

[top](#index)