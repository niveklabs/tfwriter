# newrelic_infra_alert_condition

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
module "newrelic_infra_alert_condition" {
  source = "./modules/newrelic/r/newrelic_infra_alert_condition"

  # comparison - (optional) is a type of string
  comparison = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # event - (optional) is a type of string
  event = null
  # integration_provider - (optional) is a type of string
  integration_provider = null
  # name - (required) is a type of string
  name = null
  # policy_id - (required) is a type of number
  policy_id = null
  # process_where - (optional) is a type of string
  process_where = null
  # runbook_url - (optional) is a type of string
  runbook_url = null
  # select - (optional) is a type of string
  select = null
  # type - (required) is a type of string
  type = null
  # violation_close_timer - (optional) is a type of number
  violation_close_timer = null
  # where - (optional) is a type of string
  where = null

  critical = [{
    duration      = null
    time_function = null
    value         = null
  }]

  warning = [{
    duration      = null
    time_function = null
    value         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comparison" {
  description = "(optional) - The operator used to evaluate the threshold value. Valid values are above, below, and equal. Supported by the infra_metric and infra_process_running condition types."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - The description of the Infrastructure alert condition."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Whether the condition is turned on or off. Valid values are true and false. Defaults to true."
  type        = bool
  default     = null
}

variable "event" {
  description = "(optional) - The metric event; for example, SystemSample or StorageSample. Supported by the infra_metric condition type."
  type        = string
  default     = null
}

variable "integration_provider" {
  description = "(optional) - For alerts on integrations, use this instead of event. Supported by the infra_metric condition type."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The Infrastructure alert condition's name."
  type        = string
}

variable "policy_id" {
  description = "(required) - The ID of the alert policy where this condition should be used."
  type        = number
}

variable "process_where" {
  description = "(optional) - Any filters applied to processes; for example: commandName = 'java'. Supported by the infra_process_running condition type."
  type        = string
  default     = null
}

variable "runbook_url" {
  description = "(optional) - Runbook URL to display in notifications."
  type        = string
  default     = null
}

variable "select" {
  description = "(optional) - The attribute name to identify the metric being targeted; for example, cpuPercent, diskFreePercent, or memoryResidentSizeBytes. The underlying API will automatically populate this value for Infrastructure integrations (for example diskFreePercent), so make sure to explicitly include this value to avoid diff issues. Supported by the infra_metric condition type."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - The type of Infrastructure alert condition. Valid values are infra_process_running, infra_metric, and infra_host_not_reporting."
  type        = string
}

variable "violation_close_timer" {
  description = "(optional) - Determines how much time, in minutes, will pass before a violation is automatically closed. Setting the time limit to 0 prevents a violation from being force-closed. Valid values are 0, 1, 2, 4, 8, 12, 24, 48, or 72"
  type        = number
  default     = null
}

variable "where" {
  description = "(optional) - If applicable, this identifies any Infrastructure host filters used; for example: hostname LIKE '%cassandra%'."
  type        = string
  default     = null
}

variable "critical" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      duration      = number
      time_function = string
      value         = number
    }
  ))
  default = []
}

variable "warning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      duration      = number
      time_function = string
      value         = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_infra_alert_condition" "this" {
  comparison            = var.comparison
  description           = var.description
  enabled               = var.enabled
  event                 = var.event
  integration_provider  = var.integration_provider
  name                  = var.name
  policy_id             = var.policy_id
  process_where         = var.process_where
  runbook_url           = var.runbook_url
  select                = var.select
  type                  = var.type
  violation_close_timer = var.violation_close_timer
  where                 = var.where

  dynamic "critical" {
    for_each = var.critical
    content {
      duration      = critical.value["duration"]
      time_function = critical.value["time_function"]
      value         = critical.value["value"]
    }
  }

  dynamic "warning" {
    for_each = var.warning
    content {
      duration      = warning.value["duration"]
      time_function = warning.value["time_function"]
      value         = warning.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a number"
  value       = newrelic_infra_alert_condition.this.created_at
}

output "event" {
  description = "returns a string"
  value       = newrelic_infra_alert_condition.this.event
}

output "id" {
  description = "returns a string"
  value       = newrelic_infra_alert_condition.this.id
}

output "updated_at" {
  description = "returns a number"
  value       = newrelic_infra_alert_condition.this.updated_at
}

output "this" {
  value = newrelic_infra_alert_condition.this
}
```

[top](#index)