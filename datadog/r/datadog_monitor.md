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
    datadog = ">= 2.18.1"
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
}
```

[top](#index)

### Variables

```terraform
variable "enable_logs_sample" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "escalation_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "evaluation_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "force_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "include_tags" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "locked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "message" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "new_host_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "no_data_timeframe" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notify_audit" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "notify_no_data" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "query" {
  description = "(required)"
  type        = string
}

variable "renotify_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "require_full_window" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "silenced" {
  description = "(optional)"
  type        = map(number)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "threshold_windows" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "thresholds" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeout_h" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "validate" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_monitor" "this" {
  enable_logs_sample  = var.enable_logs_sample
  escalation_message  = var.escalation_message
  evaluation_delay    = var.evaluation_delay
  force_delete        = var.force_delete
  include_tags        = var.include_tags
  locked              = var.locked
  message             = var.message
  name                = var.name
  new_host_delay      = var.new_host_delay
  no_data_timeframe   = var.no_data_timeframe
  notify_audit        = var.notify_audit
  notify_no_data      = var.notify_no_data
  priority            = var.priority
  query               = var.query
  renotify_interval   = var.renotify_interval
  require_full_window = var.require_full_window
  silenced            = var.silenced
  tags                = var.tags
  threshold_windows   = var.threshold_windows
  thresholds          = var.thresholds
  timeout_h           = var.timeout_h
  type                = var.type
  validate            = var.validate
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