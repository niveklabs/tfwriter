# datadog_monitor

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_monitor" {
  source = "./modules/datadog/d/datadog_monitor"

  # monitor_tags_filter - (optional) is a type of list of string
  monitor_tags_filter = []
  # name_filter - (optional) is a type of string
  name_filter = null
  # tags_filter - (optional) is a type of list of string
  tags_filter = []
}
```

[top](#index)

### Variables

```terraform
variable "monitor_tags_filter" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags_filter" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "datadog_monitor" "this" {
  monitor_tags_filter = var.monitor_tags_filter
  name_filter         = var.name_filter
  tags_filter         = var.tags_filter
}
```

[top](#index)

### Outputs

```terraform
output "enable_logs_sample" {
  description = "returns a bool"
  value       = data.datadog_monitor.this.enable_logs_sample
}

output "escalation_message" {
  description = "returns a string"
  value       = data.datadog_monitor.this.escalation_message
}

output "evaluation_delay" {
  description = "returns a number"
  value       = data.datadog_monitor.this.evaluation_delay
}

output "id" {
  description = "returns a string"
  value       = data.datadog_monitor.this.id
}

output "include_tags" {
  description = "returns a bool"
  value       = data.datadog_monitor.this.include_tags
}

output "locked" {
  description = "returns a bool"
  value       = data.datadog_monitor.this.locked
}

output "message" {
  description = "returns a string"
  value       = data.datadog_monitor.this.message
}

output "name" {
  description = "returns a string"
  value       = data.datadog_monitor.this.name
}

output "new_host_delay" {
  description = "returns a number"
  value       = data.datadog_monitor.this.new_host_delay
}

output "no_data_timeframe" {
  description = "returns a number"
  value       = data.datadog_monitor.this.no_data_timeframe
}

output "notify_audit" {
  description = "returns a bool"
  value       = data.datadog_monitor.this.notify_audit
}

output "notify_no_data" {
  description = "returns a bool"
  value       = data.datadog_monitor.this.notify_no_data
}

output "query" {
  description = "returns a string"
  value       = data.datadog_monitor.this.query
}

output "renotify_interval" {
  description = "returns a number"
  value       = data.datadog_monitor.this.renotify_interval
}

output "require_full_window" {
  description = "returns a bool"
  value       = data.datadog_monitor.this.require_full_window
}

output "tags" {
  description = "returns a set of string"
  value       = data.datadog_monitor.this.tags
}

output "threshold_windows" {
  description = "returns a map of string"
  value       = data.datadog_monitor.this.threshold_windows
}

output "thresholds" {
  description = "returns a map of string"
  value       = data.datadog_monitor.this.thresholds
}

output "timeout_h" {
  description = "returns a number"
  value       = data.datadog_monitor.this.timeout_h
}

output "type" {
  description = "returns a string"
  value       = data.datadog_monitor.this.type
}

output "this" {
  value = datadog_monitor.this
}
```

[top](#index)