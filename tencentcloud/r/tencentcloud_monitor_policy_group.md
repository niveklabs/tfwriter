# tencentcloud_monitor_policy_group

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
module "tencentcloud_monitor_policy_group" {
  source = "./modules/tencentcloud/r/tencentcloud_monitor_policy_group"

  # group_name - (required) is a type of string
  group_name = null
  # is_union_rule - (optional) is a type of number
  is_union_rule = null
  # policy_view_name - (required) is a type of string
  policy_view_name = null
  # project_id - (optional) is a type of number
  project_id = null
  # remark - (required) is a type of string
  remark = null

  conditions = [{
    alarm_notify_period = null
    alarm_notify_type   = null
    calc_period         = null
    calc_type           = null
    calc_value          = null
    continue_period     = null
    metric_id           = null
  }]

  event_conditions = [{
    alarm_notify_period = null
    alarm_notify_type   = null
    event_id            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required) - Policy group name, length should between 1 and 20."
  type        = string
}

variable "is_union_rule" {
  description = "(optional) - The and or relation of indicator alarm rule. Valid values: `0`, `1`. `0` represents or rule (if any rule is met, the alarm will be raised), `1` represents and rule (if all rules are met, the alarm will be raised).The default is 0."
  type        = number
  default     = null
}

variable "policy_view_name" {
  description = "(required) - Policy view name, eg:`cvm_device`,`BANDWIDTHPACKAGE`, refer to `data.tencentcloud_monitor_policy_conditions(policy_view_name)`."
  type        = string
}

variable "project_id" {
  description = "(optional) - The project id to which the policy group belongs, default is `0`."
  type        = number
  default     = null
}

variable "remark" {
  description = "(required) - Policy group's remark information."
  type        = string
}

variable "conditions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alarm_notify_period = number
      alarm_notify_type   = number
      calc_period         = number
      calc_type           = number
      calc_value          = number
      continue_period     = number
      metric_id           = number
    }
  ))
  default = []
}

variable "event_conditions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alarm_notify_period = number
      alarm_notify_type   = number
      event_id            = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_monitor_policy_group" "this" {
  group_name       = var.group_name
  is_union_rule    = var.is_union_rule
  policy_view_name = var.policy_view_name
  project_id       = var.project_id
  remark           = var.remark

  dynamic "conditions" {
    for_each = var.conditions
    content {
      alarm_notify_period = conditions.value["alarm_notify_period"]
      alarm_notify_type   = conditions.value["alarm_notify_type"]
      calc_period         = conditions.value["calc_period"]
      calc_type           = conditions.value["calc_type"]
      calc_value          = conditions.value["calc_value"]
      continue_period     = conditions.value["continue_period"]
      metric_id           = conditions.value["metric_id"]
    }
  }

  dynamic "event_conditions" {
    for_each = var.event_conditions
    content {
      alarm_notify_period = event_conditions.value["alarm_notify_period"]
      alarm_notify_type   = event_conditions.value["alarm_notify_type"]
      event_id            = event_conditions.value["event_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "binding_objects" {
  description = "returns a list of object"
  value       = tencentcloud_monitor_policy_group.this.binding_objects
}

output "dimension_group" {
  description = "returns a list of string"
  value       = tencentcloud_monitor_policy_group.this.dimension_group
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_monitor_policy_group.this.id
}

output "last_edit_uin" {
  description = "returns a string"
  value       = tencentcloud_monitor_policy_group.this.last_edit_uin
}

output "receivers" {
  description = "returns a list of object"
  value       = tencentcloud_monitor_policy_group.this.receivers
}

output "support_regions" {
  description = "returns a list of string"
  value       = tencentcloud_monitor_policy_group.this.support_regions
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_monitor_policy_group.this.update_time
}

output "this" {
  value = tencentcloud_monitor_policy_group.this
}
```

[top](#index)