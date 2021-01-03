# newrelic_synthetics_multilocation_alert_condition

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
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_synthetics_multilocation_alert_condition" {
  source = "./modules/newrelic/r/newrelic_synthetics_multilocation_alert_condition"

  # enabled - (optional) is a type of bool
  enabled = null
  # entities - (required) is a type of list of string
  entities = []
  # name - (required) is a type of string
  name = null
  # policy_id - (required) is a type of number
  policy_id = null
  # runbook_url - (optional) is a type of string
  runbook_url = null
  # violation_time_limit_seconds - (required) is a type of number
  violation_time_limit_seconds = null

  critical = [{
    threshold = null
  }]

  warning = [{
    threshold = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Set whether to enable the alert condition. Defaults to true."
  type        = bool
  default     = null
}

variable "entities" {
  description = "(required) - The GUIDs of the Synthetics monitors to alert on."
  type        = list(string)
}

variable "name" {
  description = "(required) - The title of this condition."
  type        = string
}

variable "policy_id" {
  description = "(required) - The ID of the policy where this condition will be used."
  type        = number
}

variable "runbook_url" {
  description = "(optional) - Runbook URL to display in notifications."
  type        = string
  default     = null
}

variable "violation_time_limit_seconds" {
  description = "(required) - The maximum number of seconds a violation can remain open before being closed by the system.  Must be one of: 0, 3600, 7200, 14400, 28800, 43200, 86400"
  type        = number
}

variable "critical" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      threshold = number
    }
  ))
}

variable "warning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      threshold = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_synthetics_multilocation_alert_condition" "this" {
  enabled                      = var.enabled
  entities                     = var.entities
  name                         = var.name
  policy_id                    = var.policy_id
  runbook_url                  = var.runbook_url
  violation_time_limit_seconds = var.violation_time_limit_seconds

  dynamic "critical" {
    for_each = var.critical
    content {
      threshold = critical.value["threshold"]
    }
  }

  dynamic "warning" {
    for_each = var.warning
    content {
      threshold = warning.value["threshold"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_synthetics_multilocation_alert_condition.this.id
}

output "this" {
  value = newrelic_synthetics_multilocation_alert_condition.this
}
```

[top](#index)