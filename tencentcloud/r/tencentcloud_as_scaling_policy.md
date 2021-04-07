# tencentcloud_as_scaling_policy

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_as_scaling_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_as_scaling_policy"

  # adjustment_type - (required) is a type of string
  adjustment_type = null
  # adjustment_value - (required) is a type of number
  adjustment_value = null
  # comparison_operator - (required) is a type of string
  comparison_operator = null
  # continuous_time - (required) is a type of number
  continuous_time = null
  # cooldown - (optional) is a type of number
  cooldown = null
  # metric_name - (required) is a type of string
  metric_name = null
  # notification_user_group_ids - (optional) is a type of list of string
  notification_user_group_ids = []
  # period - (required) is a type of number
  period = null
  # policy_name - (required) is a type of string
  policy_name = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
  # statistic - (optional) is a type of string
  statistic = null
  # threshold - (required) is a type of number
  threshold = null
}
```

[top](#index)

### Variables

```terraform
variable "adjustment_type" {
  description = "(required) - Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values: `CHANGE_IN_CAPACITY`, `EXACT_CAPACITY` and `PERCENT_CHANGE_IN_CAPACITY`."
  type        = string
}

variable "adjustment_value" {
  description = "(required) - Define the number of instances by which to scale.For `CHANGE_IN_CAPACITY` type or PERCENT_CHANGE_IN_CAPACITY, a positive increment adds to the current capacity and a negative value removes from the current capacity. For `EXACT_CAPACITY` type, it defines an absolute number of the existing Auto Scaling group size."
  type        = number
}

variable "comparison_operator" {
  description = "(required) - Comparison operator. Valid values: `GREATER_THAN`, `GREATER_THAN_OR_EQUAL_TO`, `LESS_THAN`, `LESS_THAN_OR_EQUAL_TO`, `EQUAL_TO` and `NOT_EQUAL_TO`."
  type        = string
}

variable "continuous_time" {
  description = "(required) - Retry times. Valid value ranges: (1~10)."
  type        = number
}

variable "cooldown" {
  description = "(optional) - Cooldwon time in second. Default is `30`0."
  type        = number
  default     = null
}

variable "metric_name" {
  description = "(required) - Name of an indicator. Valid values: `CPU_UTILIZATION`, `MEM_UTILIZATION`, `LAN_TRAFFIC_OUT`, `LAN_TRAFFIC_IN`, `WAN_TRAFFIC_OUT` and `WAN_TRAFFIC_IN`."
  type        = string
}

variable "notification_user_group_ids" {
  description = "(optional) - An ID group of users to be notified when an alarm is triggered."
  type        = list(string)
  default     = null
}

variable "period" {
  description = "(required) - Time period in second. Valid values: `60` and `300`."
  type        = number
}

variable "policy_name" {
  description = "(required) - Name of a policy used to define a reaction when an alarm is triggered."
  type        = string
}

variable "scaling_group_id" {
  description = "(required) - ID of a scaling group."
  type        = string
}

variable "statistic" {
  description = "(optional) - Statistic types. Valid values: `AVERAGE`, `MAXIMUM` and `MINIMUM`. Default is `AVERAGE`."
  type        = string
  default     = null
}

variable "threshold" {
  description = "(required) - Alarm threshold."
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_as_scaling_policy" "this" {
  adjustment_type             = var.adjustment_type
  adjustment_value            = var.adjustment_value
  comparison_operator         = var.comparison_operator
  continuous_time             = var.continuous_time
  cooldown                    = var.cooldown
  metric_name                 = var.metric_name
  notification_user_group_ids = var.notification_user_group_ids
  period                      = var.period
  policy_name                 = var.policy_name
  scaling_group_id            = var.scaling_group_id
  statistic                   = var.statistic
  threshold                   = var.threshold
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_as_scaling_policy.this.id
}

output "this" {
  value = tencentcloud_as_scaling_policy.this
}
```

[top](#index)