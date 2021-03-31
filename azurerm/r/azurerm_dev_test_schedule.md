# azurerm_dev_test_schedule

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
module "azurerm_dev_test_schedule" {
  source = "./modules/azurerm/r/azurerm_dev_test_schedule"

  # lab_name - (required) is a type of string
  lab_name = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # task_type - (required) is a type of string
  task_type = null
  # time_zone_id - (required) is a type of string
  time_zone_id = null

  daily_recurrence = [{
    time = null
  }]

  hourly_recurrence = [{
    minute = null
  }]

  notification_settings = [{
    status          = null
    time_in_minutes = null
    webhook_url     = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  weekly_recurrence = [{
    time      = null
    week_days = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "lab_name" {
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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "task_type" {
  description = "(required)"
  type        = string
}

variable "time_zone_id" {
  description = "(required)"
  type        = string
}

variable "daily_recurrence" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      time = string
    }
  ))
  default = []
}

variable "hourly_recurrence" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      minute = number
    }
  ))
  default = []
}

variable "notification_settings" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      status          = string
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

variable "weekly_recurrence" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      time      = string
      week_days = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_dev_test_schedule" "this" {
  lab_name            = var.lab_name
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  status              = var.status
  tags                = var.tags
  task_type           = var.task_type
  time_zone_id        = var.time_zone_id

  dynamic "daily_recurrence" {
    for_each = var.daily_recurrence
    content {
      time = daily_recurrence.value["time"]
    }
  }

  dynamic "hourly_recurrence" {
    for_each = var.hourly_recurrence
    content {
      minute = hourly_recurrence.value["minute"]
    }
  }

  dynamic "notification_settings" {
    for_each = var.notification_settings
    content {
      status          = notification_settings.value["status"]
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

  dynamic "weekly_recurrence" {
    for_each = var.weekly_recurrence
    content {
      time      = weekly_recurrence.value["time"]
      week_days = weekly_recurrence.value["week_days"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_dev_test_schedule.this.id
}

output "this" {
  value = azurerm_dev_test_schedule.this
}
```

[top](#index)