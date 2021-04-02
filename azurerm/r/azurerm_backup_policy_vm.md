# azurerm_backup_policy_vm

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
module "azurerm_backup_policy_vm" {
  source = "./modules/azurerm/r/azurerm_backup_policy_vm"

  # instant_restore_retention_days - (optional) is a type of number
  instant_restore_retention_days = null
  # name - (required) is a type of string
  name = null
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timezone - (optional) is a type of string
  timezone = null

  backup = [{
    frequency = null
    time      = null
    weekdays  = []
  }]

  retention_daily = [{
    count = null
  }]

  retention_monthly = [{
    count    = null
    weekdays = []
    weeks    = []
  }]

  retention_weekly = [{
    count    = null
    weekdays = []
  }]

  retention_yearly = [{
    count    = null
    months   = []
    weekdays = []
    weeks    = []
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
variable "instant_restore_retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
      weekdays  = set(string)
    }
  ))
}

variable "retention_daily" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      count = number
    }
  ))
  default = []
}

variable "retention_monthly" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      count    = number
      weekdays = set(string)
      weeks    = set(string)
    }
  ))
  default = []
}

variable "retention_weekly" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      count    = number
      weekdays = set(string)
    }
  ))
  default = []
}

variable "retention_yearly" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      count    = number
      months   = set(string)
      weekdays = set(string)
      weeks    = set(string)
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
resource "azurerm_backup_policy_vm" "this" {
  instant_restore_retention_days = var.instant_restore_retention_days
  name                           = var.name
  recovery_vault_name            = var.recovery_vault_name
  resource_group_name            = var.resource_group_name
  tags                           = var.tags
  timezone                       = var.timezone

  dynamic "backup" {
    for_each = var.backup
    content {
      frequency = backup.value["frequency"]
      time      = backup.value["time"]
      weekdays  = backup.value["weekdays"]
    }
  }

  dynamic "retention_daily" {
    for_each = var.retention_daily
    content {
      count = retention_daily.value["count"]
    }
  }

  dynamic "retention_monthly" {
    for_each = var.retention_monthly
    content {
      count    = retention_monthly.value["count"]
      weekdays = retention_monthly.value["weekdays"]
      weeks    = retention_monthly.value["weeks"]
    }
  }

  dynamic "retention_weekly" {
    for_each = var.retention_weekly
    content {
      count    = retention_weekly.value["count"]
      weekdays = retention_weekly.value["weekdays"]
    }
  }

  dynamic "retention_yearly" {
    for_each = var.retention_yearly
    content {
      count    = retention_yearly.value["count"]
      months   = retention_yearly.value["months"]
      weekdays = retention_yearly.value["weekdays"]
      weeks    = retention_yearly.value["weeks"]
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
  value       = azurerm_backup_policy_vm.this.id
}

output "instant_restore_retention_days" {
  description = "returns a number"
  value       = azurerm_backup_policy_vm.this.instant_restore_retention_days
}

output "this" {
  value = azurerm_backup_policy_vm.this
}
```

[top](#index)