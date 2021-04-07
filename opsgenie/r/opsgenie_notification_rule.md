# opsgenie_notification_rule

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_notification_rule" {
  source = "./modules/opsgenie/r/opsgenie_notification_rule"

  # action_type - (required) is a type of string
  action_type = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # notification_time - (optional) is a type of set of string
  notification_time = []
  # order - (optional) is a type of number
  order = null
  # username - (required) is a type of string
  username = null

  criteria = [{
    conditions = [{
      expected_value = null
      field          = null
      key            = null
      not            = null
      operation      = null
      order          = null
    }]
    type = null
  }]

  repeat = [{
    enabled    = null
    loop_after = null
  }]

  schedules = [{
    name = null
    type = null
  }]

  steps = [{
    contact = [{
      method = null
      to     = null
    }]
    enabled    = null
    send_after = null
  }]

  time_restriction = [{
    restriction = [{
      end_hour   = null
      end_min    = null
      start_hour = null
      start_min  = null
    }]
    restrictions = [{
      end_day    = null
      end_hour   = null
      end_min    = null
      start_day  = null
      start_hour = null
      start_min  = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action_type" {
  description = "(required)"
  type        = string
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

variable "notification_time" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "order" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "criteria" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      conditions = list(object(
        {
          expected_value = string
          field          = string
          key            = string
          not            = bool
          operation      = string
          order          = number
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "repeat" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enabled    = bool
      loop_after = number
    }
  ))
  default = []
}

variable "schedules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      type = string
    }
  ))
  default = []
}

variable "steps" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      contact = list(object(
        {
          method = string
          to     = string
        }
      ))
      enabled    = bool
      send_after = number
    }
  ))
  default = []
}

variable "time_restriction" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      restriction = list(object(
        {
          end_hour   = number
          end_min    = number
          start_hour = number
          start_min  = number
        }
      ))
      restrictions = list(object(
        {
          end_day    = string
          end_hour   = number
          end_min    = number
          start_day  = string
          start_hour = number
          start_min  = number
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
resource "opsgenie_notification_rule" "this" {
  # action_type - (required) is a type of string
  action_type = var.action_type
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # notification_time - (optional) is a type of set of string
  notification_time = var.notification_time
  # order - (optional) is a type of number
  order = var.order
  # username - (required) is a type of string
  username = var.username

  dynamic "criteria" {
    for_each = var.criteria
    content {
      # type - (required) is a type of string
      type = criteria.value["type"]

      dynamic "conditions" {
        for_each = criteria.value.conditions
        content {
          # expected_value - (optional) is a type of string
          expected_value = conditions.value["expected_value"]
          # field - (required) is a type of string
          field = conditions.value["field"]
          # key - (optional) is a type of string
          key = conditions.value["key"]
          # not - (optional) is a type of bool
          not = conditions.value["not"]
          # operation - (required) is a type of string
          operation = conditions.value["operation"]
          # order - (optional) is a type of number
          order = conditions.value["order"]
        }
      }

    }
  }

  dynamic "repeat" {
    for_each = var.repeat
    content {
      # enabled - (optional) is a type of bool
      enabled = repeat.value["enabled"]
      # loop_after - (required) is a type of number
      loop_after = repeat.value["loop_after"]
    }
  }

  dynamic "schedules" {
    for_each = var.schedules
    content {
      # name - (required) is a type of string
      name = schedules.value["name"]
      # type - (required) is a type of string
      type = schedules.value["type"]
    }
  }

  dynamic "steps" {
    for_each = var.steps
    content {
      # enabled - (optional) is a type of bool
      enabled = steps.value["enabled"]
      # send_after - (optional) is a type of number
      send_after = steps.value["send_after"]

      dynamic "contact" {
        for_each = steps.value.contact
        content {
          # method - (required) is a type of string
          method = contact.value["method"]
          # to - (required) is a type of string
          to = contact.value["to"]
        }
      }

    }
  }

  dynamic "time_restriction" {
    for_each = var.time_restriction
    content {
      # type - (required) is a type of string
      type = time_restriction.value["type"]

      dynamic "restriction" {
        for_each = time_restriction.value.restriction
        content {
          # end_hour - (required) is a type of number
          end_hour = restriction.value["end_hour"]
          # end_min - (required) is a type of number
          end_min = restriction.value["end_min"]
          # start_hour - (required) is a type of number
          start_hour = restriction.value["start_hour"]
          # start_min - (required) is a type of number
          start_min = restriction.value["start_min"]
        }
      }

      dynamic "restrictions" {
        for_each = time_restriction.value.restrictions
        content {
          # end_day - (required) is a type of string
          end_day = restrictions.value["end_day"]
          # end_hour - (required) is a type of number
          end_hour = restrictions.value["end_hour"]
          # end_min - (required) is a type of number
          end_min = restrictions.value["end_min"]
          # start_day - (required) is a type of string
          start_day = restrictions.value["start_day"]
          # start_hour - (required) is a type of number
          start_hour = restrictions.value["start_hour"]
          # start_min - (required) is a type of number
          start_min = restrictions.value["start_min"]
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
  value       = opsgenie_notification_rule.this.id
}

output "order" {
  description = "returns a number"
  value       = opsgenie_notification_rule.this.order
}

output "this" {
  value = opsgenie_notification_rule.this
}
```

[top](#index)