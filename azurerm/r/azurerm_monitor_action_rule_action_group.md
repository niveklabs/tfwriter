# azurerm_monitor_action_rule_action_group

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
module "azurerm_monitor_action_rule_action_group" {
  source = "./modules/azurerm/r/azurerm_monitor_action_rule_action_group"

  # action_group_id - (required) is a type of string
  action_group_id = null
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
variable "action_group_id" {
  description = "(required)"
  type        = string
}

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
resource "azurerm_monitor_action_rule_action_group" "this" {
  # action_group_id - (required) is a type of string
  action_group_id = var.action_group_id
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "condition" {
    for_each = var.condition
    content {

      dynamic "alert_context" {
        for_each = condition.value.alert_context
        content {
          # operator - (required) is a type of string
          operator = alert_context.value["operator"]
          # values - (required) is a type of set of string
          values = alert_context.value["values"]
        }
      }

      dynamic "alert_rule_id" {
        for_each = condition.value.alert_rule_id
        content {
          # operator - (required) is a type of string
          operator = alert_rule_id.value["operator"]
          # values - (required) is a type of set of string
          values = alert_rule_id.value["values"]
        }
      }

      dynamic "description" {
        for_each = condition.value.description
        content {
          # operator - (required) is a type of string
          operator = description.value["operator"]
          # values - (required) is a type of set of string
          values = description.value["values"]
        }
      }

      dynamic "monitor" {
        for_each = condition.value.monitor
        content {
          # operator - (required) is a type of string
          operator = monitor.value["operator"]
          # values - (required) is a type of set of string
          values = monitor.value["values"]
        }
      }

      dynamic "monitor_service" {
        for_each = condition.value.monitor_service
        content {
          # operator - (required) is a type of string
          operator = monitor_service.value["operator"]
          # values - (required) is a type of set of string
          values = monitor_service.value["values"]
        }
      }

      dynamic "severity" {
        for_each = condition.value.severity
        content {
          # operator - (required) is a type of string
          operator = severity.value["operator"]
          # values - (required) is a type of set of string
          values = severity.value["values"]
        }
      }

      dynamic "target_resource_type" {
        for_each = condition.value.target_resource_type
        content {
          # operator - (required) is a type of string
          operator = target_resource_type.value["operator"]
          # values - (required) is a type of set of string
          values = target_resource_type.value["values"]
        }
      }

    }
  }

  dynamic "scope" {
    for_each = var.scope
    content {
      # resource_ids - (required) is a type of set of string
      resource_ids = scope.value["resource_ids"]
      # type - (required) is a type of string
      type = scope.value["type"]
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
  value       = azurerm_monitor_action_rule_action_group.this.id
}

output "this" {
  value = azurerm_monitor_action_rule_action_group.this
}
```

[top](#index)