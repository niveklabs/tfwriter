# opsgenie_notification_policy

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
module "opsgenie_notification_policy" {
  source = "./modules/opsgenie/r/opsgenie_notification_policy"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # policy_description - (optional) is a type of string
  policy_description = null
  # suppress - (optional) is a type of bool
  suppress = null
  # team_id - (required) is a type of string
  team_id = null

  auto_close_action = [{
    duration = [{
      time_amount = null
      time_unit   = null
    }]
  }]

  auto_restart_action = [{
    duration = [{
      time_amount = null
      time_unit   = null
    }]
    max_repeat_count = null
  }]

  de_duplication_action = [{
    count                      = null
    de_duplication_action_type = null
    duration = [{
      time_amount = null
      time_unit   = null
    }]
  }]

  delay_action = [{
    delay_option = null
    duration = [{
      time_amount = null
      time_unit   = null
    }]
    until_hour   = null
    until_minute = null
  }]

  filter = [{
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
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suppress" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "team_id" {
  description = "(required)"
  type        = string
}

variable "auto_close_action" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      duration = list(object(
        {
          time_amount = number
          time_unit   = string
        }
      ))
    }
  ))
  default = []
}

variable "auto_restart_action" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      duration = list(object(
        {
          time_amount = number
          time_unit   = string
        }
      ))
      max_repeat_count = number
    }
  ))
  default = []
}

variable "de_duplication_action" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      count                      = number
      de_duplication_action_type = string
      duration = list(object(
        {
          time_amount = number
          time_unit   = string
        }
      ))
    }
  ))
  default = []
}

variable "delay_action" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      delay_option = string
      duration = list(object(
        {
          time_amount = number
          time_unit   = string
        }
      ))
      until_hour   = number
      until_minute = number
    }
  ))
  default = []
}

variable "filter" {
  description = "nested block: NestingList, min items: 1, max items: 0"
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
resource "opsgenie_notification_policy" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # policy_description - (optional) is a type of string
  policy_description = var.policy_description
  # suppress - (optional) is a type of bool
  suppress = var.suppress
  # team_id - (required) is a type of string
  team_id = var.team_id

  dynamic "auto_close_action" {
    for_each = var.auto_close_action
    content {

      dynamic "duration" {
        for_each = auto_close_action.value.duration
        content {
          # time_amount - (required) is a type of number
          time_amount = duration.value["time_amount"]
          # time_unit - (optional) is a type of string
          time_unit = duration.value["time_unit"]
        }
      }

    }
  }

  dynamic "auto_restart_action" {
    for_each = var.auto_restart_action
    content {
      # max_repeat_count - (required) is a type of number
      max_repeat_count = auto_restart_action.value["max_repeat_count"]

      dynamic "duration" {
        for_each = auto_restart_action.value.duration
        content {
          # time_amount - (required) is a type of number
          time_amount = duration.value["time_amount"]
          # time_unit - (optional) is a type of string
          time_unit = duration.value["time_unit"]
        }
      }

    }
  }

  dynamic "de_duplication_action" {
    for_each = var.de_duplication_action
    content {
      # count - (required) is a type of number
      count = de_duplication_action.value["count"]
      # de_duplication_action_type - (required) is a type of string
      de_duplication_action_type = de_duplication_action.value["de_duplication_action_type"]

      dynamic "duration" {
        for_each = de_duplication_action.value.duration
        content {
          # time_amount - (required) is a type of number
          time_amount = duration.value["time_amount"]
          # time_unit - (optional) is a type of string
          time_unit = duration.value["time_unit"]
        }
      }

    }
  }

  dynamic "delay_action" {
    for_each = var.delay_action
    content {
      # delay_option - (required) is a type of string
      delay_option = delay_action.value["delay_option"]
      # until_hour - (optional) is a type of number
      until_hour = delay_action.value["until_hour"]
      # until_minute - (optional) is a type of number
      until_minute = delay_action.value["until_minute"]

      dynamic "duration" {
        for_each = delay_action.value.duration
        content {
          # time_amount - (required) is a type of number
          time_amount = duration.value["time_amount"]
          # time_unit - (optional) is a type of string
          time_unit = duration.value["time_unit"]
        }
      }

    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      # type - (optional) is a type of string
      type = filter.value["type"]

      dynamic "conditions" {
        for_each = filter.value.conditions
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
  value       = opsgenie_notification_policy.this.id
}

output "this" {
  value = opsgenie_notification_policy.this
}
```

[top](#index)