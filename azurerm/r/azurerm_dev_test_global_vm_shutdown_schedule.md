# azurerm_dev_test_global_vm_shutdown_schedule

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
module "azurerm_dev_test_global_vm_shutdown_schedule" {
  source = "./modules/azurerm/r/azurerm_dev_test_global_vm_shutdown_schedule"

  # daily_recurrence_time - (required) is a type of string
  daily_recurrence_time = null
  # enabled - (optional) is a type of bool
  enabled = null
  # location - (required) is a type of string
  location = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timezone - (required) is a type of string
  timezone = null
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null

  notification_settings = [{
    enabled         = null
    time_in_minutes = null
    webhook_url     = null
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
variable "daily_recurrence_time" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timezone" {
  description = "(required)"
  type        = string
}

variable "virtual_machine_id" {
  description = "(required)"
  type        = string
}

variable "notification_settings" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      enabled         = bool
      time_in_minutes = number
      webhook_url     = string
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
resource "azurerm_dev_test_global_vm_shutdown_schedule" "this" {
  daily_recurrence_time = var.daily_recurrence_time
  enabled               = var.enabled
  location              = var.location
  tags                  = var.tags
  timezone              = var.timezone
  virtual_machine_id    = var.virtual_machine_id

  dynamic "notification_settings" {
    for_each = var.notification_settings
    content {
      enabled         = notification_settings.value["enabled"]
      time_in_minutes = notification_settings.value["time_in_minutes"]
      webhook_url     = notification_settings.value["webhook_url"]
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
  value       = azurerm_dev_test_global_vm_shutdown_schedule.this.id
}

output "this" {
  value = azurerm_dev_test_global_vm_shutdown_schedule.this
}
```

[top](#index)