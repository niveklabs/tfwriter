# alicloud_ess_scaling_rule

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
module "alicloud_ess_scaling_rule" {
  source = "./modules/alicloud/r/alicloud_ess_scaling_rule"

  # adjustment_type - (optional) is a type of string
  adjustment_type = null
  # adjustment_value - (optional) is a type of number
  adjustment_value = null
  # cooldown - (optional) is a type of number
  cooldown = null
  # disable_scale_in - (optional) is a type of bool
  disable_scale_in = null
  # estimated_instance_warmup - (optional) is a type of number
  estimated_instance_warmup = null
  # metric_name - (optional) is a type of string
  metric_name = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
  # scaling_rule_name - (optional) is a type of string
  scaling_rule_name = null
  # scaling_rule_type - (optional) is a type of string
  scaling_rule_type = null
  # target_value - (optional) is a type of number
  target_value = null

  step_adjustment = [{
    metric_interval_lower_bound = null
    metric_interval_upper_bound = null
    scaling_adjustment          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "adjustment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "adjustment_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cooldown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_scale_in" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "estimated_instance_warmup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metric_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
}

variable "scaling_rule_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_rule_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "step_adjustment" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      metric_interval_lower_bound = string
      metric_interval_upper_bound = string
      scaling_adjustment          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_scaling_rule" "this" {
  # adjustment_type - (optional) is a type of string
  adjustment_type = var.adjustment_type
  # adjustment_value - (optional) is a type of number
  adjustment_value = var.adjustment_value
  # cooldown - (optional) is a type of number
  cooldown = var.cooldown
  # disable_scale_in - (optional) is a type of bool
  disable_scale_in = var.disable_scale_in
  # estimated_instance_warmup - (optional) is a type of number
  estimated_instance_warmup = var.estimated_instance_warmup
  # metric_name - (optional) is a type of string
  metric_name = var.metric_name
  # scaling_group_id - (required) is a type of string
  scaling_group_id = var.scaling_group_id
  # scaling_rule_name - (optional) is a type of string
  scaling_rule_name = var.scaling_rule_name
  # scaling_rule_type - (optional) is a type of string
  scaling_rule_type = var.scaling_rule_type
  # target_value - (optional) is a type of number
  target_value = var.target_value

  dynamic "step_adjustment" {
    for_each = var.step_adjustment
    content {
      # metric_interval_lower_bound - (optional) is a type of string
      metric_interval_lower_bound = step_adjustment.value["metric_interval_lower_bound"]
      # metric_interval_upper_bound - (optional) is a type of string
      metric_interval_upper_bound = step_adjustment.value["metric_interval_upper_bound"]
      # scaling_adjustment - (optional) is a type of number
      scaling_adjustment = step_adjustment.value["scaling_adjustment"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ari" {
  description = "returns a string"
  value       = alicloud_ess_scaling_rule.this.ari
}

output "estimated_instance_warmup" {
  description = "returns a number"
  value       = alicloud_ess_scaling_rule.this.estimated_instance_warmup
}

output "id" {
  description = "returns a string"
  value       = alicloud_ess_scaling_rule.this.id
}

output "scaling_rule_name" {
  description = "returns a string"
  value       = alicloud_ess_scaling_rule.this.scaling_rule_name
}

output "this" {
  value = alicloud_ess_scaling_rule.this
}
```

[top](#index)