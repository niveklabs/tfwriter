# azurerm_automation_schedule

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
module "azurerm_automation_schedule" {
  source = "./modules/azurerm/r/azurerm_automation_schedule"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # description - (optional) is a type of string
  description = null
  # expiry_time - (optional) is a type of string
  expiry_time = null
  # frequency - (required) is a type of string
  frequency = null
  # interval - (optional) is a type of number
  interval = null
  # month_days - (optional) is a type of set of number
  month_days = []
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # start_time - (optional) is a type of string
  start_time = null
  # timezone - (optional) is a type of string
  timezone = null
  # week_days - (optional) is a type of set of string
  week_days = []

  monthly_occurrence = [{
    day        = null
    occurrence = null
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
variable "automation_account_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiry_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frequency" {
  description = "(required)"
  type        = string
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "month_days" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "week_days" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "monthly_occurrence" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      day        = string
      occurrence = number
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
resource "azurerm_automation_schedule" "this" {
  automation_account_name = var.automation_account_name
  description             = var.description
  expiry_time             = var.expiry_time
  frequency               = var.frequency
  interval                = var.interval
  month_days              = var.month_days
  name                    = var.name
  resource_group_name     = var.resource_group_name
  start_time              = var.start_time
  timezone                = var.timezone
  week_days               = var.week_days

  dynamic "monthly_occurrence" {
    for_each = var.monthly_occurrence
    content {
      day        = monthly_occurrence.value["day"]
      occurrence = monthly_occurrence.value["occurrence"]
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
output "expiry_time" {
  description = "returns a string"
  value       = azurerm_automation_schedule.this.expiry_time
}

output "id" {
  description = "returns a string"
  value       = azurerm_automation_schedule.this.id
}

output "interval" {
  description = "returns a number"
  value       = azurerm_automation_schedule.this.interval
}

output "start_time" {
  description = "returns a string"
  value       = azurerm_automation_schedule.this.start_time
}

output "this" {
  value = azurerm_automation_schedule.this
}
```

[top](#index)