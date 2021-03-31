# newrelic_alert_muting_rule

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_alert_muting_rule" {
  source = "./modules/newrelic/r/newrelic_alert_muting_rule"

  # account_id - (optional) is a type of number
  account_id = null
  # description - (optional) is a type of string
  description = null
  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null

  condition = [{
    conditions = [{
      attribute = null
      operator  = null
      values    = []
    }]
    operator = null
  }]

  schedule = [{
    end_repeat         = null
    end_time           = null
    repeat             = null
    repeat_count       = null
    start_time         = null
    time_zone          = null
    weekly_repeat_days = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The account id of the MutingRule.."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The description of the MutingRule."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(required) - Whether the MutingRule is enabled."
  type        = bool
}

variable "name" {
  description = "(required) - The name of the MutingRule."
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      conditions = list(object(
        {
          attribute = string
          operator  = string
          values    = list(string)
        }
      ))
      operator = string
    }
  ))
}

variable "schedule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      end_repeat         = string
      end_time           = string
      repeat             = string
      repeat_count       = number
      start_time         = string
      time_zone          = string
      weekly_repeat_days = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_alert_muting_rule" "this" {
  account_id  = var.account_id
  description = var.description
  enabled     = var.enabled
  name        = var.name

  dynamic "condition" {
    for_each = var.condition
    content {
      operator = condition.value["operator"]

      dynamic "conditions" {
        for_each = condition.value.conditions
        content {
          attribute = conditions.value["attribute"]
          operator  = conditions.value["operator"]
          values    = conditions.value["values"]
        }
      }

    }
  }

  dynamic "schedule" {
    for_each = var.schedule
    content {
      end_repeat         = schedule.value["end_repeat"]
      end_time           = schedule.value["end_time"]
      repeat             = schedule.value["repeat"]
      repeat_count       = schedule.value["repeat_count"]
      start_time         = schedule.value["start_time"]
      time_zone          = schedule.value["time_zone"]
      weekly_repeat_days = schedule.value["weekly_repeat_days"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_alert_muting_rule.this.account_id
}

output "id" {
  description = "returns a string"
  value       = newrelic_alert_muting_rule.this.id
}

output "this" {
  value = newrelic_alert_muting_rule.this
}
```

[top](#index)