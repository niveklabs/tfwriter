# alicloud_cms_alarm

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cms_alarm" {
  source = "./modules/alicloud/r/alicloud_cms_alarm"

  # contact_groups - (required) is a type of list of string
  contact_groups = []
  # dimensions - (required) is a type of map of string
  dimensions = {}
  # effective_interval - (optional) is a type of string
  effective_interval = null
  # enabled - (optional) is a type of bool
  enabled = null
  # end_time - (optional) is a type of number
  end_time = null
  # metric - (required) is a type of string
  metric = null
  # name - (required) is a type of string
  name = null
  # notify_type - (optional) is a type of number
  notify_type = null
  # operator - (optional) is a type of string
  operator = null
  # period - (optional) is a type of number
  period = null
  # project - (required) is a type of string
  project = null
  # silence_time - (optional) is a type of number
  silence_time = null
  # start_time - (optional) is a type of number
  start_time = null
  # statistics - (optional) is a type of string
  statistics = null
  # threshold - (optional) is a type of string
  threshold = null
  # triggered_count - (optional) is a type of number
  triggered_count = null
  # webhook - (optional) is a type of string
  webhook = null

  escalations_critical = [{
    comparison_operator = null
    statistics          = null
    threshold           = null
    times               = null
  }]

  escalations_info = [{
    comparison_operator = null
    statistics          = null
    threshold           = null
    times               = null
  }]

  escalations_warn = [{
    comparison_operator = null
    statistics          = null
    threshold           = null
    times               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "contact_groups" {
  description = "(required)"
  type        = list(string)
}

variable "dimensions" {
  description = "(required)"
  type        = map(string)
}

variable "effective_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "end_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metric" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notify_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "operator" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "silence_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "start_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "statistics" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "triggered_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "webhook" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "escalations_critical" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comparison_operator = string
      statistics          = string
      threshold           = string
      times               = number
    }
  ))
  default = []
}

variable "escalations_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comparison_operator = string
      statistics          = string
      threshold           = string
      times               = number
    }
  ))
  default = []
}

variable "escalations_warn" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comparison_operator = string
      statistics          = string
      threshold           = string
      times               = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cms_alarm" "this" {
  contact_groups     = var.contact_groups
  dimensions         = var.dimensions
  effective_interval = var.effective_interval
  enabled            = var.enabled
  end_time           = var.end_time
  metric             = var.metric
  name               = var.name
  notify_type        = var.notify_type
  operator           = var.operator
  period             = var.period
  project            = var.project
  silence_time       = var.silence_time
  start_time         = var.start_time
  statistics         = var.statistics
  threshold          = var.threshold
  triggered_count    = var.triggered_count
  webhook            = var.webhook

  dynamic "escalations_critical" {
    for_each = var.escalations_critical
    content {
      comparison_operator = escalations_critical.value["comparison_operator"]
      statistics          = escalations_critical.value["statistics"]
      threshold           = escalations_critical.value["threshold"]
      times               = escalations_critical.value["times"]
    }
  }

  dynamic "escalations_info" {
    for_each = var.escalations_info
    content {
      comparison_operator = escalations_info.value["comparison_operator"]
      statistics          = escalations_info.value["statistics"]
      threshold           = escalations_info.value["threshold"]
      times               = escalations_info.value["times"]
    }
  }

  dynamic "escalations_warn" {
    for_each = var.escalations_warn
    content {
      comparison_operator = escalations_warn.value["comparison_operator"]
      statistics          = escalations_warn.value["statistics"]
      threshold           = escalations_warn.value["threshold"]
      times               = escalations_warn.value["times"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cms_alarm.this.id
}

output "operator" {
  description = "returns a string"
  value       = alicloud_cms_alarm.this.operator
}

output "statistics" {
  description = "returns a string"
  value       = alicloud_cms_alarm.this.statistics
}

output "status" {
  description = "returns a string"
  value       = alicloud_cms_alarm.this.status
}

output "threshold" {
  description = "returns a string"
  value       = alicloud_cms_alarm.this.threshold
}

output "triggered_count" {
  description = "returns a number"
  value       = alicloud_cms_alarm.this.triggered_count
}

output "this" {
  value = alicloud_cms_alarm.this
}
```

[top](#index)