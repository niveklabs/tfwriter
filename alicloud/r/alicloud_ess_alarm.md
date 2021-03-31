# alicloud_ess_alarm

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ess_alarm" {
  source = "./modules/alicloud/r/alicloud_ess_alarm"

  # alarm_actions - (required) is a type of set of string
  alarm_actions = []
  # cloud_monitor_group_id - (optional) is a type of number
  cloud_monitor_group_id = null
  # comparison_operator - (optional) is a type of string
  comparison_operator = null
  # description - (optional) is a type of string
  description = null
  # dimensions - (optional) is a type of map of string
  dimensions = {}
  # enable - (optional) is a type of bool
  enable = null
  # evaluation_count - (optional) is a type of number
  evaluation_count = null
  # metric_name - (required) is a type of string
  metric_name = null
  # metric_type - (optional) is a type of string
  metric_type = null
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
  # statistics - (optional) is a type of string
  statistics = null
  # threshold - (required) is a type of string
  threshold = null
}
```

[top](#index)

### Variables

```terraform
variable "alarm_actions" {
  description = "(required)"
  type        = set(string)
}

variable "cloud_monitor_group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comparison_operator" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dimensions" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "evaluation_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metric_name" {
  description = "(required)"
  type        = string
}

variable "metric_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
}

variable "statistics" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_alarm" "this" {
  alarm_actions          = var.alarm_actions
  cloud_monitor_group_id = var.cloud_monitor_group_id
  comparison_operator    = var.comparison_operator
  description            = var.description
  dimensions             = var.dimensions
  enable                 = var.enable
  evaluation_count       = var.evaluation_count
  metric_name            = var.metric_name
  metric_type            = var.metric_type
  name                   = var.name
  period                 = var.period
  scaling_group_id       = var.scaling_group_id
  statistics             = var.statistics
  threshold              = var.threshold
}
```

[top](#index)

### Outputs

```terraform
output "dimensions" {
  description = "returns a map of string"
  value       = alicloud_ess_alarm.this.dimensions
}

output "id" {
  description = "returns a string"
  value       = alicloud_ess_alarm.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_ess_alarm.this.name
}

output "state" {
  description = "returns a string"
  value       = alicloud_ess_alarm.this.state
}

output "this" {
  value = alicloud_ess_alarm.this
}
```

[top](#index)