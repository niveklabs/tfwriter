# azurerm_monitor_action_rule_suppression

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
module "azurerm_monitor_action_rule_suppression" {
  source = "./modules/azurerm/r/azurerm_monitor_action_rule_suppression"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  condition = [{
    alert_context = [{
      operator = null
      values   = []
    }]
    alert_rule_id = [{
      operator = null
      values   = []
    }]
    description = [{
      operator = null
      values   = []
    }]
    monitor = [{
      operator = null
      values   = []
    }]
    monitor_service = [{
      operator = null
      values   = []
    }]
    severity = [{
      operator = null
      values   = []
    }]
    target_resource_type = [{
      operator = null
      values   = []
    }]
  }]

  scope = [{
    resource_ids = []
    type         = null
  }]

  suppression = [{
    recurrence_type = null
    schedule = [{
      end_date_utc       = null
      recurrence_monthly = []
      recurrence_weekly  = []
      start_date_utc     = null
    }]
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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      alert_context = list(object(
        {
          operator = string
          values   = set(string)
        }
      ))
      alert_rule_id = list(object(
        {
          operator = string
          values   = set(string)
        }
      ))
      description = list(object(
        {
          operator = string
          values   = set(string)
        }
      ))
      monitor = list(object(
        {
          operator = string
          values   = set(string)
        }
      ))
      monitor_service = list(object(
        {
          operator = string
          values   = set(string)
        }
      ))
      severity = list(object(
        {
          operator = string
          values   = set(string)
        }
      ))
      target_resource_type = list(object(
        {
          operator = string
          values   = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "scope" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      resource_ids = set(string)
      type         = string
    }
  ))
  default = []
}

variable "suppression" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      recurrence_type = string
      schedule = list(object(
        {
          end_date_utc       = string
          recurrence_monthly = set(number)
          recurrence_weekly  = set(string)
          start_date_utc     = string
        }
      ))
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
resource "azurerm_monitor_action_rule_suppression" "this" {
  description         = var.description
  enabled             = var.enabled
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "condition" {
    for_each = var.condition
    content {

      dynamic "alert_context" {
        for_each = condition.value.alert_context
        content {
          operator = alert_context.value["operator"]
          values   = alert_context.value["values"]
        }
      }

      dynamic "alert_rule_id" {
        for_each = condition.value.alert_rule_id
        content {
          operator = alert_rule_id.value["operator"]
          values   = alert_rule_id.value["values"]
        }
      }

      dynamic "description" {
        for_each = condition.value.description
        content {
          operator = description.value["operator"]
          values   = description.value["values"]
        }
      }

      dynamic "monitor" {
        for_each = condition.value.monitor
        content {
          operator = monitor.value["operator"]
          values   = monitor.value["values"]
        }
      }

      dynamic "monitor_service" {
        for_each = condition.value.monitor_service
        content {
          operator = monitor_service.value["operator"]
          values   = monitor_service.value["values"]
        }
      }

      dynamic "severity" {
        for_each = condition.value.severity
        content {
          operator = severity.value["operator"]
          values   = severity.value["values"]
        }
      }

      dynamic "target_resource_type" {
        for_each = condition.value.target_resource_type
        content {
          operator = target_resource_type.value["operator"]
          values   = target_resource_type.value["values"]
        }
      }

    }
  }

  dynamic "scope" {
    for_each = var.scope
    content {
      resource_ids = scope.value["resource_ids"]
      type         = scope.value["type"]
    }
  }

  dynamic "suppression" {
    for_each = var.suppression
    content {
      recurrence_type = suppression.value["recurrence_type"]

      dynamic "schedule" {
        for_each = suppression.value.schedule
        content {
          end_date_utc       = schedule.value["end_date_utc"]
          recurrence_monthly = schedule.value["recurrence_monthly"]
          recurrence_weekly  = schedule.value["recurrence_weekly"]
          start_date_utc     = schedule.value["start_date_utc"]
        }
      }

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
  value       = azurerm_monitor_action_rule_suppression.this.id
}

output "this" {
  value = azurerm_monitor_action_rule_suppression.this
}
```

[top](#index)