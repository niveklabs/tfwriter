# datadog_monitor

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_monitor" {
  source = "./modules/datadog/r/datadog_monitor"

  # enable_logs_sample - (optional) is a type of bool
  enable_logs_sample = null
  # escalation_message - (optional) is a type of string
  escalation_message = null
  # evaluation_delay - (optional) is a type of number
  evaluation_delay = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # groupby_simple_monitor - (optional) is a type of bool
  groupby_simple_monitor = null
  # include_tags - (optional) is a type of bool
  include_tags = null
  # locked - (optional) is a type of bool
  locked = null
  # message - (required) is a type of string
  message = null
  # name - (required) is a type of string
  name = null
  # new_host_delay - (optional) is a type of number
  new_host_delay = null
  # no_data_timeframe - (optional) is a type of number
  no_data_timeframe = null
  # notify_audit - (optional) is a type of bool
  notify_audit = null
  # notify_no_data - (optional) is a type of bool
  notify_no_data = null
  # priority - (optional) is a type of number
  priority = null
  # query - (required) is a type of string
  query = null
  # renotify_interval - (optional) is a type of number
  renotify_interval = null
  # require_full_window - (optional) is a type of bool
  require_full_window = null
  # restricted_roles - (optional) is a type of set of string
  restricted_roles = []
  # silenced - (optional) is a type of map of number
  silenced = {}
  # tags - (optional) is a type of set of string
  tags = []
  # threshold_windows - (optional) is a type of map of string
  threshold_windows = {}
  # thresholds - (optional) is a type of map of string
  thresholds = {}
  # timeout_h - (optional) is a type of number
  timeout_h = null
  # type - (required) is a type of string
  type = null
  # validate - (optional) is a type of bool
  validate = null

  monitor_threshold_windows = [{
    recovery_window = null
    trigger_window  = null
  }]

  monitor_thresholds = [{
    critical          = null
    critical_recovery = null
    ok                = null
    unknown           = null
    warning           = null
    warning_recovery  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_logs_sample" {
  description = "(optional) - A boolean indicating whether or not to include a list of log values which triggered the alert. This is only used by log monitors. Defaults to `false`."
  type        = bool
  default     = null
}

variable "escalation_message" {
  description = "(optional) - A message to include with a re-notification. Supports the `@username` notification allowed elsewhere."
  type        = string
  default     = null
}

variable "evaluation_delay" {
  description = "(optional) - (Only applies to metric alert) Time (in seconds) to delay evaluation, as a non-negative integer.\n\nFor example, if the value is set to `300` (5min), the `timeframe` is set to `last_5m` and the time is 7:00, the monitor will evaluate data from 6:50 to 6:55. This is useful for AWS CloudWatch and other backfilled metrics to ensure the monitor will always have data during evaluation."
  type        = number
  default     = null
}

variable "force_delete" {
  description = "(optional) - A boolean indicating whether this monitor can be deleted even if it’s referenced by other resources (e.g. SLO, composite monitor)."
  type        = bool
  default     = null
}

variable "groupby_simple_monitor" {
  description = "(optional) - Whether or not to trigger one alert if any source breaches a threshold. This is only used by log monitors. Defaults to `false`."
  type        = bool
  default     = null
}

variable "include_tags" {
  description = "(optional) - A boolean indicating whether notifications from this monitor automatically insert its triggering tags into the title. Defaults to `true`."
  type        = bool
  default     = null
}

variable "locked" {
  description = "(optional) - A boolean indicating whether changes to to this monitor should be restricted to the creator or admins. Defaults to `false`."
  type        = bool
  default     = null
}

variable "message" {
  description = "(required) - A message to include with notifications for this monitor.\n\nEmail notifications can be sent to specific users by using the same `@username` notation as events."
  type        = string
}

variable "name" {
  description = "(required) - Name of Datadog monitor."
  type        = string
}

variable "new_host_delay" {
  description = "(optional) - Time (in seconds) to allow a host to boot and applications to fully start before starting the evaluation of monitor results. Should be a non negative integer. Defaults to `300`."
  type        = number
  default     = null
}

variable "no_data_timeframe" {
  description = "(optional) - The number of minutes before a monitor will notify when data stops reporting. Provider defaults to 10 minutes.\n\nWe recommend at least 2x the monitor timeframe for metric alerts or 2 minutes for service checks."
  type        = number
  default     = null
}

variable "notify_audit" {
  description = "(optional) - A boolean indicating whether tagged users will be notified on changes to this monitor. Defaults to `false`."
  type        = bool
  default     = null
}

variable "notify_no_data" {
  description = "(optional) - A boolean indicating whether this monitor will notify when data stops reporting. Defaults to `false`."
  type        = bool
  default     = null
}

variable "priority" {
  description = "(optional) - Integer from 1 (high) to 5 (low) indicating alert severity."
  type        = number
  default     = null
}

variable "query" {
  description = "(required) - The monitor query to notify on. Note this is not the same query you see in the UI and the syntax is different depending on the monitor type, please see the [API Reference](https://docs.datadoghq.com/api/v1/monitors/#create-a-monitor) for details. `terraform plan` will validate query contents unless `validate` is set to `false`.\n\n**Note:** APM latency data is now available as Distribution Metrics. Existing monitors have been migrated automatically but all terraformed monitors can still use the existing metrics. We strongly recommend updating monitor definitions to query the new metrics. To learn more, or to see examples of how to update your terraform definitions to utilize the new distribution metrics, see the [detailed doc](https://docs.datadoghq.com/tracing/guide/ddsketch_trace_metrics/)."
  type        = string
}

variable "renotify_interval" {
  description = "(optional) - The number of minutes after the last notification before a monitor will re-notify on the current status. It will only re-notify if it's not resolved."
  type        = number
  default     = null
}

variable "require_full_window" {
  description = "(optional) - A boolean indicating whether this monitor needs a full window of data before it's evaluated.\n\nWe highly recommend you set this to `false` for sparse metrics, otherwise some evaluations will be skipped. Default: `true` for `on average`, `at all times` and `in total` aggregation. `false` otherwise."
  type        = bool
  default     = null
}

variable "restricted_roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "silenced" {
  description = "(optional) - Each scope will be muted until the given POSIX timestamp or forever if the value is `0`. Use `-1` if you want to unmute the scope. Deprecated: the silenced parameter is being deprecated in favor of the downtime resource. This will be removed in the next major version of the Terraform Provider. **Deprecated.** Use the Downtime resource instead."
  type        = map(number)
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tags to associate with your monitor. This can help you categorize and filter monitors in the manage monitors page of the UI. Note: it's not currently possible to filter by these tags when querying via the API"
  type        = set(string)
  default     = null
}

variable "threshold_windows" {
  description = "(optional) - A mapping containing `recovery_window` and `trigger_window` values, e.g. `last_15m`. Can only be used for, and are required for, anomaly monitors. **Deprecated.** Define `monitor_threshold_windows` list with one element instead."
  type        = map(string)
  default     = null
}

variable "thresholds" {
  description = "(optional) - Alert thresholds of the monitor. **Deprecated.** Define `monitor_thresholds` list with one element instead."
  type        = map(string)
  default     = null
}

variable "timeout_h" {
  description = "(optional) - The number of hours of the monitor not reporting data before it will automatically resolve from a triggered state."
  type        = number
  default     = null
}

variable "type" {
  description = "(required) - The type of the monitor. The mapping from these types to the types found in the Datadog Web UI can be found in the Datadog API [documentation page](https://docs.datadoghq.com/api/v1/monitors/#create-a-monitor). Note: The monitor type cannot be changed after a monitor is created."
  type        = string
}

variable "validate" {
  description = "(optional) - If set to `false`, skip the validation call done during plan."
  type        = bool
  default     = null
}

variable "monitor_threshold_windows" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      recovery_window = string
      trigger_window  = string
    }
  ))
  default = []
}

variable "monitor_thresholds" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      critical          = string
      critical_recovery = string
      ok                = string
      unknown           = string
      warning           = string
      warning_recovery  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_monitor" "this" {
  enable_logs_sample     = var.enable_logs_sample
  escalation_message     = var.escalation_message
  evaluation_delay       = var.evaluation_delay
  force_delete           = var.force_delete
  groupby_simple_monitor = var.groupby_simple_monitor
  include_tags           = var.include_tags
  locked                 = var.locked
  message                = var.message
  name                   = var.name
  new_host_delay         = var.new_host_delay
  no_data_timeframe      = var.no_data_timeframe
  notify_audit           = var.notify_audit
  notify_no_data         = var.notify_no_data
  priority               = var.priority
  query                  = var.query
  renotify_interval      = var.renotify_interval
  require_full_window    = var.require_full_window
  restricted_roles       = var.restricted_roles
  silenced               = var.silenced
  tags                   = var.tags
  threshold_windows      = var.threshold_windows
  thresholds             = var.thresholds
  timeout_h              = var.timeout_h
  type                   = var.type
  validate               = var.validate

  dynamic "monitor_threshold_windows" {
    for_each = var.monitor_threshold_windows
    content {
      recovery_window = monitor_threshold_windows.value["recovery_window"]
      trigger_window  = monitor_threshold_windows.value["trigger_window"]
    }
  }

  dynamic "monitor_thresholds" {
    for_each = var.monitor_thresholds
    content {
      critical          = monitor_thresholds.value["critical"]
      critical_recovery = monitor_thresholds.value["critical_recovery"]
      ok                = monitor_thresholds.value["ok"]
      unknown           = monitor_thresholds.value["unknown"]
      warning           = monitor_thresholds.value["warning"]
      warning_recovery  = monitor_thresholds.value["warning_recovery"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "evaluation_delay" {
  description = "returns a number"
  value       = datadog_monitor.this.evaluation_delay
}

output "id" {
  description = "returns a string"
  value       = datadog_monitor.this.id
}

output "this" {
  value = datadog_monitor.this
}
```

[top](#index)