# aws_autoscaling_policy

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_autoscaling_policy" {
  source = "./modules/aws/r/aws_autoscaling_policy"

  # adjustment_type - (optional) is a type of string
  adjustment_type = null
  # autoscaling_group_name - (required) is a type of string
  autoscaling_group_name = null
  # cooldown - (optional) is a type of number
  cooldown = null
  # estimated_instance_warmup - (optional) is a type of number
  estimated_instance_warmup = null
  # metric_aggregation_type - (optional) is a type of string
  metric_aggregation_type = null
  # min_adjustment_magnitude - (optional) is a type of number
  min_adjustment_magnitude = null
  # name - (required) is a type of string
  name = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # scaling_adjustment - (optional) is a type of number
  scaling_adjustment = null

  step_adjustment = [{
    metric_interval_lower_bound = null
    metric_interval_upper_bound = null
    scaling_adjustment          = null
  }]

  target_tracking_configuration = [{
    customized_metric_specification = [{
      metric_dimension = [{
        name  = null
        value = null
      }]
      metric_name = null
      namespace   = null
      statistic   = null
      unit        = null
    }]
    disable_scale_in = null
    predefined_metric_specification = [{
      predefined_metric_type = null
      resource_label         = null
    }]
    target_value = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "adjustment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autoscaling_group_name" {
  description = "(required)"
  type        = string
}

variable "cooldown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "estimated_instance_warmup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metric_aggregation_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_adjustment_magnitude" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_adjustment" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "step_adjustment" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      metric_interval_lower_bound = string
      metric_interval_upper_bound = string
      scaling_adjustment          = number
    }
  ))
  default = []
}

variable "target_tracking_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      customized_metric_specification = list(object(
        {
          metric_dimension = list(object(
            {
              name  = string
              value = string
            }
          ))
          metric_name = string
          namespace   = string
          statistic   = string
          unit        = string
        }
      ))
      disable_scale_in = bool
      predefined_metric_specification = list(object(
        {
          predefined_metric_type = string
          resource_label         = string
        }
      ))
      target_value = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_autoscaling_policy" "this" {
  adjustment_type           = var.adjustment_type
  autoscaling_group_name    = var.autoscaling_group_name
  cooldown                  = var.cooldown
  estimated_instance_warmup = var.estimated_instance_warmup
  metric_aggregation_type   = var.metric_aggregation_type
  min_adjustment_magnitude  = var.min_adjustment_magnitude
  name                      = var.name
  policy_type               = var.policy_type
  scaling_adjustment        = var.scaling_adjustment

  dynamic "step_adjustment" {
    for_each = var.step_adjustment
    content {
      metric_interval_lower_bound = step_adjustment.value["metric_interval_lower_bound"]
      metric_interval_upper_bound = step_adjustment.value["metric_interval_upper_bound"]
      scaling_adjustment          = step_adjustment.value["scaling_adjustment"]
    }
  }

  dynamic "target_tracking_configuration" {
    for_each = var.target_tracking_configuration
    content {
      disable_scale_in = target_tracking_configuration.value["disable_scale_in"]
      target_value     = target_tracking_configuration.value["target_value"]

      dynamic "customized_metric_specification" {
        for_each = target_tracking_configuration.value.customized_metric_specification
        content {
          metric_name = customized_metric_specification.value["metric_name"]
          namespace   = customized_metric_specification.value["namespace"]
          statistic   = customized_metric_specification.value["statistic"]
          unit        = customized_metric_specification.value["unit"]

          dynamic "metric_dimension" {
            for_each = customized_metric_specification.value.metric_dimension
            content {
              name  = metric_dimension.value["name"]
              value = metric_dimension.value["value"]
            }
          }

        }
      }

      dynamic "predefined_metric_specification" {
        for_each = target_tracking_configuration.value.predefined_metric_specification
        content {
          predefined_metric_type = predefined_metric_specification.value["predefined_metric_type"]
          resource_label         = predefined_metric_specification.value["resource_label"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_autoscaling_policy.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_autoscaling_policy.this.id
}

output "metric_aggregation_type" {
  description = "returns a string"
  value       = aws_autoscaling_policy.this.metric_aggregation_type
}

output "this" {
  value = aws_autoscaling_policy.this
}
```

[top](#index)