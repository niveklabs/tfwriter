# opsgenie_team_routing_rule

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
module "opsgenie_team_routing_rule" {
  source = "./modules/opsgenie/r/opsgenie_team_routing_rule"

  # name - (optional) is a type of string
  name = null
  # order - (optional) is a type of number
  order = null
  # team_id - (required) is a type of string
  team_id = null
  # timezone - (optional) is a type of string
  timezone = null

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

  notify = [{
    id   = null
    name = null
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
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "order" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "team_id" {
  description = "(required)"
  type        = string
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "notify" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
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
resource "opsgenie_team_routing_rule" "this" {
  # name - (optional) is a type of string
  name = var.name
  # order - (optional) is a type of number
  order = var.order
  # team_id - (required) is a type of string
  team_id = var.team_id
  # timezone - (optional) is a type of string
  timezone = var.timezone

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

  dynamic "notify" {
    for_each = var.notify
    content {
      # id - (optional) is a type of string
      id = notify.value["id"]
      # name - (optional) is a type of string
      name = notify.value["name"]
      # type - (required) is a type of string
      type = notify.value["type"]
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
  value       = opsgenie_team_routing_rule.this.id
}

output "this" {
  value = opsgenie_team_routing_rule.this
}
```

[top](#index)