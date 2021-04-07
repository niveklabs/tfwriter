# newrelic_nrql_alert_condition

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
module "newrelic_nrql_alert_condition" {
  source = "./modules/newrelic/r/newrelic_nrql_alert_condition"

  # account_id - (optional) is a type of number
  account_id = null
  # aggregation_window - (optional) is a type of number
  aggregation_window = null
  # baseline_direction - (optional) is a type of string
  baseline_direction = null
  # close_violations_on_expiration - (optional) is a type of bool
  close_violations_on_expiration = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # expected_groups - (optional) is a type of number
  expected_groups = null
  # expiration_duration - (optional) is a type of number
  expiration_duration = null
  # fill_option - (optional) is a type of string
  fill_option = null
  # fill_value - (optional) is a type of number
  fill_value = null
  # ignore_overlap - (optional) is a type of bool
  ignore_overlap = null
  # name - (required) is a type of string
  name = null
  # open_violation_on_expiration - (optional) is a type of bool
  open_violation_on_expiration = null
  # open_violation_on_group_overlap - (optional) is a type of bool
  open_violation_on_group_overlap = null
  # policy_id - (required) is a type of number
  policy_id = null
  # runbook_url - (optional) is a type of string
  runbook_url = null
  # type - (optional) is a type of string
  type = null
  # value_function - (optional) is a type of string
  value_function = null
  # violation_time_limit - (optional) is a type of string
  violation_time_limit = null
  # violation_time_limit_seconds - (optional) is a type of number
  violation_time_limit_seconds = null

  critical = [{
    duration              = null
    operator              = null
    threshold             = null
    threshold_duration    = null
    threshold_occurrences = null
    time_function         = null
  }]

  nrql = [{
    evaluation_offset = null
    query             = null
    since_value       = null
  }]

  term = [{
    duration              = null
    operator              = null
    priority              = null
    threshold             = null
    threshold_duration    = null
    threshold_occurrences = null
    time_function         = null
  }]

  warning = [{
    duration              = null
    operator              = null
    threshold             = null
    threshold_duration    = null
    threshold_occurrences = null
    time_function         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The New Relic account ID for managing your NRQL alert conditions."
  type        = number
  default     = null
}

variable "aggregation_window" {
  description = "(optional) - The duration of the time window used to evaluate the NRQL query, in seconds."
  type        = number
  default     = null
}

variable "baseline_direction" {
  description = "(optional) - The baseline direction of a baseline NRQL alert condition. Valid values are: 'LOWER_ONLY', 'UPPER_AND_LOWER', 'UPPER_ONLY' (case insensitive)."
  type        = string
  default     = null
}

variable "close_violations_on_expiration" {
  description = "(optional) - Whether to close all open violations when the signal expires."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - The description of the NRQL alert condition."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Whether or not to enable the alert condition."
  type        = bool
  default     = null
}

variable "expected_groups" {
  description = "(optional) - Number of expected groups when using outlier detection."
  type        = number
  default     = null
}

variable "expiration_duration" {
  description = "(optional) - The amount of time (in seconds) to wait before considering the signal expired."
  type        = number
  default     = null
}

variable "fill_option" {
  description = "(optional) - Which strategy to use when filling gaps in the signal. If static, the 'fill value' will be used for filling gaps in the signal. Valid values are: 'NONE', 'LAST_VALUE', or 'STATIC' (case insensitive)."
  type        = string
  default     = null
}

variable "fill_value" {
  description = "(optional) - If using the 'static' fill option, this value will be used for filling gaps in the signal."
  type        = number
  default     = null
}

variable "ignore_overlap" {
  description = "(optional) - Whether to look for a convergence of groups when using outlier detection."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The title of the condition."
  type        = string
}

variable "open_violation_on_expiration" {
  description = "(optional) - Whether to create a new violation to capture that the signal expired."
  type        = bool
  default     = null
}

variable "open_violation_on_group_overlap" {
  description = "(optional) - Whether overlapping groups should produce a violation."
  type        = bool
  default     = null
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
  description = "(optional) - The type of NRQL alert condition to create. Valid values are: 'static', 'outlier', 'baseline'."
  type        = string
  default     = null
}

variable "value_function" {
  description = "(optional) - Valid values are: 'single_value' or 'sum'"
  type        = string
  default     = null
}

variable "violation_time_limit" {
  description = "(optional) - Sets a time limit, in hours, that will automatically force-close a long-lasting violation after the time limit you select. Possible values are 'ONE_HOUR', 'TWO_HOURS', 'FOUR_HOURS', 'EIGHT_HOURS', 'TWELVE_HOURS', 'TWENTY_FOUR_HOURS', 'THIRTY_DAYS' (case insensitive)."
  type        = string
  default     = null
}

variable "violation_time_limit_seconds" {
  description = "(optional) - Sets a time limit, in seconds, that will automatically force-close a long-lasting violation after the time limit you select.  Must be in the range of 300 to 2592000 (inclusive)"
  type        = number
  default     = null
}

variable "critical" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      duration              = number
      operator              = string
      threshold             = number
      threshold_duration    = number
      threshold_occurrences = string
      time_function         = string
    }
  ))
  default = []
}

variable "nrql" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      evaluation_offset = number
      query             = string
      since_value       = string
    }
  ))
}

variable "term" {
  description = "nested block: NestingSet, min items: 0, max items: 2"
  type = set(object(
    {
      duration              = number
      operator              = string
      priority              = string
      threshold             = number
      threshold_duration    = number
      threshold_occurrences = string
      time_function         = string
    }
  ))
  default = []
}

variable "warning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      duration              = number
      operator              = string
      threshold             = number
      threshold_duration    = number
      threshold_occurrences = string
      time_function         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_nrql_alert_condition" "this" {
  # account_id - (optional) is a type of number
  account_id = var.account_id
  # aggregation_window - (optional) is a type of number
  aggregation_window = var.aggregation_window
  # baseline_direction - (optional) is a type of string
  baseline_direction = var.baseline_direction
  # close_violations_on_expiration - (optional) is a type of bool
  close_violations_on_expiration = var.close_violations_on_expiration
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # expected_groups - (optional) is a type of number
  expected_groups = var.expected_groups
  # expiration_duration - (optional) is a type of number
  expiration_duration = var.expiration_duration
  # fill_option - (optional) is a type of string
  fill_option = var.fill_option
  # fill_value - (optional) is a type of number
  fill_value = var.fill_value
  # ignore_overlap - (optional) is a type of bool
  ignore_overlap = var.ignore_overlap
  # name - (required) is a type of string
  name = var.name
  # open_violation_on_expiration - (optional) is a type of bool
  open_violation_on_expiration = var.open_violation_on_expiration
  # open_violation_on_group_overlap - (optional) is a type of bool
  open_violation_on_group_overlap = var.open_violation_on_group_overlap
  # policy_id - (required) is a type of number
  policy_id = var.policy_id
  # runbook_url - (optional) is a type of string
  runbook_url = var.runbook_url
  # type - (optional) is a type of string
  type = var.type
  # value_function - (optional) is a type of string
  value_function = var.value_function
  # violation_time_limit - (optional) is a type of string
  violation_time_limit = var.violation_time_limit
  # violation_time_limit_seconds - (optional) is a type of number
  violation_time_limit_seconds = var.violation_time_limit_seconds

  dynamic "critical" {
    for_each = var.critical
    content {
      # duration - (optional) is a type of number
      duration = critical.value["duration"]
      # operator - (optional) is a type of string
      operator = critical.value["operator"]
      # threshold - (required) is a type of number
      threshold = critical.value["threshold"]
      # threshold_duration - (optional) is a type of number
      threshold_duration = critical.value["threshold_duration"]
      # threshold_occurrences - (optional) is a type of string
      threshold_occurrences = critical.value["threshold_occurrences"]
      # time_function - (optional) is a type of string
      time_function = critical.value["time_function"]
    }
  }

  dynamic "nrql" {
    for_each = var.nrql
    content {
      # evaluation_offset - (optional) is a type of number
      evaluation_offset = nrql.value["evaluation_offset"]
      # query - (required) is a type of string
      query = nrql.value["query"]
      # since_value - (optional) is a type of string
      since_value = nrql.value["since_value"]
    }
  }

  dynamic "term" {
    for_each = var.term
    content {
      # duration - (optional) is a type of number
      duration = term.value["duration"]
      # operator - (optional) is a type of string
      operator = term.value["operator"]
      # priority - (optional) is a type of string
      priority = term.value["priority"]
      # threshold - (required) is a type of number
      threshold = term.value["threshold"]
      # threshold_duration - (optional) is a type of number
      threshold_duration = term.value["threshold_duration"]
      # threshold_occurrences - (optional) is a type of string
      threshold_occurrences = term.value["threshold_occurrences"]
      # time_function - (optional) is a type of string
      time_function = term.value["time_function"]
    }
  }

  dynamic "warning" {
    for_each = var.warning
    content {
      # duration - (optional) is a type of number
      duration = warning.value["duration"]
      # operator - (optional) is a type of string
      operator = warning.value["operator"]
      # threshold - (required) is a type of number
      threshold = warning.value["threshold"]
      # threshold_duration - (optional) is a type of number
      threshold_duration = warning.value["threshold_duration"]
      # threshold_occurrences - (optional) is a type of string
      threshold_occurrences = warning.value["threshold_occurrences"]
      # time_function - (optional) is a type of string
      time_function = warning.value["time_function"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_nrql_alert_condition.this.account_id
}

output "aggregation_window" {
  description = "returns a number"
  value       = newrelic_nrql_alert_condition.this.aggregation_window
}

output "id" {
  description = "returns a string"
  value       = newrelic_nrql_alert_condition.this.id
}

output "violation_time_limit" {
  description = "returns a string"
  value       = newrelic_nrql_alert_condition.this.violation_time_limit
}

output "this" {
  value = newrelic_nrql_alert_condition.this
}
```

[top](#index)