# newrelic_plugins_alert_condition

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
module "newrelic_plugins_alert_condition" {
  source = "./modules/newrelic/r/newrelic_plugins_alert_condition"

  # enabled - (optional) is a type of bool
  enabled = null
  # entities - (required) is a type of set of number
  entities = []
  # metric - (required) is a type of string
  metric = null
  # metric_description - (required) is a type of string
  metric_description = null
  # name - (required) is a type of string
  name = null
  # plugin_guid - (required) is a type of string
  plugin_guid = null
  # plugin_id - (required) is a type of string
  plugin_id = null
  # policy_id - (required) is a type of number
  policy_id = null
  # runbook_url - (optional) is a type of string
  runbook_url = null
  # value_function - (required) is a type of string
  value_function = null

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
variable "enabled" {
  description = "(optional) - Whether or not this condition is enabled."
  type        = bool
  default     = null
}

variable "entities" {
  description = "(required) - The plugin component IDs to target."
  type        = set(number)
}

variable "metric" {
  description = "(required) - The plugin metric to evaluate."
  type        = string
}

variable "metric_description" {
  description = "(required) - The metric description."
  type        = string
}

variable "name" {
  description = "(required) - The title of the condition. Must be between 1 and 64 characters, inclusive."
  type        = string
}

variable "plugin_guid" {
  description = "(required) - The GUID of the plugin which produces the metric."
  type        = string
}

variable "plugin_id" {
  description = "(required) - The ID of the installed plugin instance which produces the metric."
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

variable "value_function" {
  description = "(required) - The value function to apply to the metric data.  One of `min`, `max`, `average`, `sample_size`, `total`, or `percent`."
  type        = string
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
resource "newrelic_plugins_alert_condition" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # entities - (required) is a type of set of number
  entities = var.entities
  # metric - (required) is a type of string
  metric = var.metric
  # metric_description - (required) is a type of string
  metric_description = var.metric_description
  # name - (required) is a type of string
  name = var.name
  # plugin_guid - (required) is a type of string
  plugin_guid = var.plugin_guid
  # plugin_id - (required) is a type of string
  plugin_id = var.plugin_id
  # policy_id - (required) is a type of number
  policy_id = var.policy_id
  # runbook_url - (optional) is a type of string
  runbook_url = var.runbook_url
  # value_function - (required) is a type of string
  value_function = var.value_function

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
  value       = newrelic_plugins_alert_condition.this.id
}

output "this" {
  value = newrelic_plugins_alert_condition.this
}
```

[top](#index)