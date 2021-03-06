# pagerduty_ruleset_rule

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_ruleset_rule" {
  source = "./modules/pagerduty/r/pagerduty_ruleset_rule"

  # disabled - (optional) is a type of bool
  disabled = null
  # position - (optional) is a type of number
  position = null
  # ruleset - (required) is a type of string
  ruleset = null

  actions = [{
    annotate = [{
      value = null
    }]
    event_action = [{
      value = null
    }]
    extractions = [{
      regex    = null
      source   = null
      target   = null
      template = null
    }]
    priority = [{
      value = null
    }]
    route = [{
      value = null
    }]
    severity = [{
      value = null
    }]
    suppress = [{
      threshold_time_amount = null
      threshold_time_unit   = null
      threshold_value       = null
      value                 = null
    }]
    suspend = [{
      value = null
    }]
  }]

  conditions = [{
    operator = null
    subconditions = [{
      operator = null
      parameter = [{
        path  = null
        value = null
      }]
    }]
  }]

  time_frame = [{
    active_between = [{
      end_time   = null
      start_time = null
    }]
    scheduled_weekly = [{
      duration   = null
      start_time = null
      timezone   = null
      weekdays   = []
    }]
  }]

  variable = [{
    name = null
    parameters = [{
      path  = null
      value = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "position" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ruleset" {
  description = "(required)"
  type        = string
}

variable "actions" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      annotate = list(object(
        {
          value = string
        }
      ))
      event_action = list(object(
        {
          value = string
        }
      ))
      extractions = list(object(
        {
          regex    = string
          source   = string
          target   = string
          template = string
        }
      ))
      priority = list(object(
        {
          value = string
        }
      ))
      route = list(object(
        {
          value = string
        }
      ))
      severity = list(object(
        {
          value = string
        }
      ))
      suppress = list(object(
        {
          threshold_time_amount = number
          threshold_time_unit   = string
          threshold_value       = number
          value                 = bool
        }
      ))
      suspend = list(object(
        {
          value = number
        }
      ))
    }
  ))
  default = []
}

variable "conditions" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      operator = string
      subconditions = list(object(
        {
          operator = string
          parameter = list(object(
            {
              path  = string
              value = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "time_frame" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      active_between = list(object(
        {
          end_time   = number
          start_time = number
        }
      ))
      scheduled_weekly = list(object(
        {
          duration   = number
          start_time = number
          timezone   = string
          weekdays   = list(number)
        }
      ))
    }
  ))
  default = []
}

variable "variable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      parameters = list(object(
        {
          path  = string
          value = string
        }
      ))
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_ruleset_rule" "this" {
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # position - (optional) is a type of number
  position = var.position
  # ruleset - (required) is a type of string
  ruleset = var.ruleset

  dynamic "actions" {
    for_each = var.actions
    content {

      dynamic "annotate" {
        for_each = actions.value.annotate
        content {
          # value - (optional) is a type of string
          value = annotate.value["value"]
        }
      }

      dynamic "event_action" {
        for_each = actions.value.event_action
        content {
          # value - (optional) is a type of string
          value = event_action.value["value"]
        }
      }

      dynamic "extractions" {
        for_each = actions.value.extractions
        content {
          # regex - (optional) is a type of string
          regex = extractions.value["regex"]
          # source - (optional) is a type of string
          source = extractions.value["source"]
          # target - (optional) is a type of string
          target = extractions.value["target"]
          # template - (optional) is a type of string
          template = extractions.value["template"]
        }
      }

      dynamic "priority" {
        for_each = actions.value.priority
        content {
          # value - (optional) is a type of string
          value = priority.value["value"]
        }
      }

      dynamic "route" {
        for_each = actions.value.route
        content {
          # value - (optional) is a type of string
          value = route.value["value"]
        }
      }

      dynamic "severity" {
        for_each = actions.value.severity
        content {
          # value - (optional) is a type of string
          value = severity.value["value"]
        }
      }

      dynamic "suppress" {
        for_each = actions.value.suppress
        content {
          # threshold_time_amount - (optional) is a type of number
          threshold_time_amount = suppress.value["threshold_time_amount"]
          # threshold_time_unit - (optional) is a type of string
          threshold_time_unit = suppress.value["threshold_time_unit"]
          # threshold_value - (optional) is a type of number
          threshold_value = suppress.value["threshold_value"]
          # value - (optional) is a type of bool
          value = suppress.value["value"]
        }
      }

      dynamic "suspend" {
        for_each = actions.value.suspend
        content {
          # value - (optional) is a type of number
          value = suspend.value["value"]
        }
      }

    }
  }

  dynamic "conditions" {
    for_each = var.conditions
    content {
      # operator - (optional) is a type of string
      operator = conditions.value["operator"]

      dynamic "subconditions" {
        for_each = conditions.value.subconditions
        content {
          # operator - (optional) is a type of string
          operator = subconditions.value["operator"]

          dynamic "parameter" {
            for_each = subconditions.value.parameter
            content {
              # path - (optional) is a type of string
              path = parameter.value["path"]
              # value - (optional) is a type of string
              value = parameter.value["value"]
            }
          }

        }
      }

    }
  }

  dynamic "time_frame" {
    for_each = var.time_frame
    content {

      dynamic "active_between" {
        for_each = time_frame.value.active_between
        content {
          # end_time - (optional) is a type of number
          end_time = active_between.value["end_time"]
          # start_time - (optional) is a type of number
          start_time = active_between.value["start_time"]
        }
      }

      dynamic "scheduled_weekly" {
        for_each = time_frame.value.scheduled_weekly
        content {
          # duration - (optional) is a type of number
          duration = scheduled_weekly.value["duration"]
          # start_time - (optional) is a type of number
          start_time = scheduled_weekly.value["start_time"]
          # timezone - (optional) is a type of string
          timezone = scheduled_weekly.value["timezone"]
          # weekdays - (optional) is a type of list of number
          weekdays = scheduled_weekly.value["weekdays"]
        }
      }

    }
  }

  dynamic "variable" {
    for_each = var.variable
    content {
      # name - (optional) is a type of string
      name = variable.value["name"]
      # type - (optional) is a type of string
      type = variable.value["type"]

      dynamic "parameters" {
        for_each = variable.value.parameters
        content {
          # path - (optional) is a type of string
          path = parameters.value["path"]
          # value - (optional) is a type of string
          value = parameters.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_ruleset_rule.this.id
}

output "this" {
  value = pagerduty_ruleset_rule.this
}
```

[top](#index)