# newrelic_alert_condition

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
module "newrelic_alert_condition" {
  source = "./modules/newrelic/r/newrelic_alert_condition"

  # condition_scope - (optional) is a type of string
  condition_scope = null
  # enabled - (optional) is a type of bool
  enabled = null
  # entities - (required) is a type of set of number
  entities = []
  # gc_metric - (optional) is a type of string
  gc_metric = null
  # metric - (required) is a type of string
  metric = null
  # name - (required) is a type of string
  name = null
  # policy_id - (required) is a type of number
  policy_id = null
  # runbook_url - (optional) is a type of string
  runbook_url = null
  # type - (required) is a type of string
  type = null
  # user_defined_metric - (optional) is a type of string
  user_defined_metric = null
  # user_defined_value_function - (optional) is a type of string
  user_defined_value_function = null
  # violation_close_timer - (optional) is a type of number
  violation_close_timer = null

  term = [{
    duration      = null
    operator      = null
    priority      = null
    threshold     = null
    time_function = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "condition_scope" {
  description = "(optional) - One of (application, instance). Choose application for most scenarios. If you are using the JVM plugin in New Relic, the instance setting allows your condition to trigger for specific app instances."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - The title of the condition. Must be between 1 and 64 characters, inclusive."
  type        = bool
  default     = null
}

variable "entities" {
  description = "(required) - The instance IDs associated with this condition."
  type        = set(number)
}

variable "gc_metric" {
  description = "(optional) - A valid Garbage Collection metric e.g. GC/G1 Young Generation. This is required if you are using apm_jvm_metric with gc_cpu_time condition type."
  type        = string
  default     = null
}

variable "metric" {
  description = "(required) - The metric field accepts parameters based on the type set."
  type        = string
}

variable "name" {
  description = "(required) - The title of the condition. Must be between 1 and 64 characters, inclusive."
  type        = string
}

variable "policy_id" {
  description = "(required) - The ID of the policy where this condition should be used."
  type        = number
}

variable "runbook_url" {
  description = "(optional) - Runbook URL to display in notifications."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - The type of condition. One of: (apm_app_metric, apm_jvm_metric, apm_kt_metric, browser_metric, mobile_metric, servers_metric)."
  type        = string
}

variable "user_defined_metric" {
  description = "(optional) - A custom metric to be evaluated."
  type        = string
  default     = null
}

variable "user_defined_value_function" {
  description = "(optional) - One of: (average, min, max, total, sample_size)."
  type        = string
  default     = null
}

variable "violation_close_timer" {
  description = "(optional) - Automatically close instance-based violations, including JVM health metric violations, after the number of hours specified. Must be: 1, 2, 4, 8, 12 or 24."
  type        = number
  default     = null
}

variable "term" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      duration      = number
      operator      = string
      priority      = string
      threshold     = number
      time_function = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_alert_condition" "this" {
  # condition_scope - (optional) is a type of string
  condition_scope = var.condition_scope
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # entities - (required) is a type of set of number
  entities = var.entities
  # gc_metric - (optional) is a type of string
  gc_metric = var.gc_metric
  # metric - (required) is a type of string
  metric = var.metric
  # name - (required) is a type of string
  name = var.name
  # policy_id - (required) is a type of number
  policy_id = var.policy_id
  # runbook_url - (optional) is a type of string
  runbook_url = var.runbook_url
  # type - (required) is a type of string
  type = var.type
  # user_defined_metric - (optional) is a type of string
  user_defined_metric = var.user_defined_metric
  # user_defined_value_function - (optional) is a type of string
  user_defined_value_function = var.user_defined_value_function
  # violation_close_timer - (optional) is a type of number
  violation_close_timer = var.violation_close_timer

  dynamic "term" {
    for_each = var.term
    content {
      # duration - (required) is a type of number
      duration = term.value["duration"]
      # operator - (optional) is a type of string
      operator = term.value["operator"]
      # priority - (optional) is a type of string
      priority = term.value["priority"]
      # threshold - (required) is a type of number
      threshold = term.value["threshold"]
      # time_function - (required) is a type of string
      time_function = term.value["time_function"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_alert_condition.this.id
}

output "this" {
  value = newrelic_alert_condition.this
}
```

[top](#index)