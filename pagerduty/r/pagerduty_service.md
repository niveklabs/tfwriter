# pagerduty_service

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
module "pagerduty_service" {
  source = "./modules/pagerduty/r/pagerduty_service"

  # acknowledgement_timeout - (optional) is a type of string
  acknowledgement_timeout = null
  # alert_creation - (optional) is a type of string
  alert_creation = null
  # alert_grouping - (optional) is a type of string
  alert_grouping = null
  # alert_grouping_timeout - (optional) is a type of number
  alert_grouping_timeout = null
  # auto_resolve_timeout - (optional) is a type of string
  auto_resolve_timeout = null
  # description - (optional) is a type of string
  description = null
  # escalation_policy - (required) is a type of string
  escalation_policy = null
  # name - (required) is a type of string
  name = null

  incident_urgency_rule = [{
    during_support_hours = [{
      type    = null
      urgency = null
    }]
    outside_support_hours = [{
      type    = null
      urgency = null
    }]
    type    = null
    urgency = null
  }]

  scheduled_actions = [{
    at = [{
      name = null
      type = null
    }]
    to_urgency = null
    type       = null
  }]

  support_hours = [{
    days_of_week = []
    end_time     = null
    start_time   = null
    time_zone    = null
    type         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acknowledgement_timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_creation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_grouping" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_grouping_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_resolve_timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "escalation_policy" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "incident_urgency_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      during_support_hours = list(object(
        {
          type    = string
          urgency = string
        }
      ))
      outside_support_hours = list(object(
        {
          type    = string
          urgency = string
        }
      ))
      type    = string
      urgency = string
    }
  ))
  default = []
}

variable "scheduled_actions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      at = list(object(
        {
          name = string
          type = string
        }
      ))
      to_urgency = string
      type       = string
    }
  ))
  default = []
}

variable "support_hours" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      days_of_week = list(number)
      end_time     = string
      start_time   = string
      time_zone    = string
      type         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_service" "this" {
  acknowledgement_timeout = var.acknowledgement_timeout
  alert_creation          = var.alert_creation
  alert_grouping          = var.alert_grouping
  alert_grouping_timeout  = var.alert_grouping_timeout
  auto_resolve_timeout    = var.auto_resolve_timeout
  description             = var.description
  escalation_policy       = var.escalation_policy
  name                    = var.name

  dynamic "incident_urgency_rule" {
    for_each = var.incident_urgency_rule
    content {
      type    = incident_urgency_rule.value["type"]
      urgency = incident_urgency_rule.value["urgency"]

      dynamic "during_support_hours" {
        for_each = incident_urgency_rule.value.during_support_hours
        content {
          type    = during_support_hours.value["type"]
          urgency = during_support_hours.value["urgency"]
        }
      }

      dynamic "outside_support_hours" {
        for_each = incident_urgency_rule.value.outside_support_hours
        content {
          type    = outside_support_hours.value["type"]
          urgency = outside_support_hours.value["urgency"]
        }
      }

    }
  }

  dynamic "scheduled_actions" {
    for_each = var.scheduled_actions
    content {
      to_urgency = scheduled_actions.value["to_urgency"]
      type       = scheduled_actions.value["type"]

      dynamic "at" {
        for_each = scheduled_actions.value.at
        content {
          name = at.value["name"]
          type = at.value["type"]
        }
      }

    }
  }

  dynamic "support_hours" {
    for_each = var.support_hours
    content {
      days_of_week = support_hours.value["days_of_week"]
      end_time     = support_hours.value["end_time"]
      start_time   = support_hours.value["start_time"]
      time_zone    = support_hours.value["time_zone"]
      type         = support_hours.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = pagerduty_service.this.created_at
}

output "html_url" {
  description = "returns a string"
  value       = pagerduty_service.this.html_url
}

output "id" {
  description = "returns a string"
  value       = pagerduty_service.this.id
}

output "last_incident_timestamp" {
  description = "returns a string"
  value       = pagerduty_service.this.last_incident_timestamp
}

output "status" {
  description = "returns a string"
  value       = pagerduty_service.this.status
}

output "this" {
  value = pagerduty_service.this
}
```

[top](#index)