# aws_appautoscaling_policy

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_appautoscaling_policy" {
  source = "./modules/aws/r/aws_appautoscaling_policy"

  # name - (required) is a type of string
  name = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # resource_id - (required) is a type of string
  resource_id = null
  # scalable_dimension - (required) is a type of string
  scalable_dimension = null
  # service_namespace - (required) is a type of string
  service_namespace = null

  step_scaling_policy_configuration = [{
    adjustment_type          = null
    cooldown                 = null
    metric_aggregation_type  = null
    min_adjustment_magnitude = null
    step_adjustment = [{
      metric_interval_lower_bound = null
      metric_interval_upper_bound = null
      scaling_adjustment          = null
    }]
  }]

  target_tracking_scaling_policy_configuration = [{
    customized_metric_specification = [{
      dimensions = [{
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
    scale_in_cooldown  = null
    scale_out_cooldown = null
    target_value       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "scalable_dimension" {
  description = "(required)"
  type        = string
}

variable "service_namespace" {
  description = "(required)"
  type        = string
}

variable "step_scaling_policy_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      adjustment_type          = string
      cooldown                 = number
      metric_aggregation_type  = string
      min_adjustment_magnitude = number
      step_adjustment = set(object(
        {
          metric_interval_lower_bound = string
          metric_interval_upper_bound = string
          scaling_adjustment          = number
        }
      ))
    }
  ))
  default = []
}

variable "target_tracking_scaling_policy_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      customized_metric_specification = list(object(
        {
          dimensions = set(object(
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
      scale_in_cooldown  = number
      scale_out_cooldown = number
      target_value       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_appautoscaling_policy" "this" {
  name               = var.name
  policy_type        = var.policy_type
  resource_id        = var.resource_id
  scalable_dimension = var.scalable_dimension
  service_namespace  = var.service_namespace

  dynamic "step_scaling_policy_configuration" {
    for_each = var.step_scaling_policy_configuration
    content {
      adjustment_type          = step_scaling_policy_configuration.value["adjustment_type"]
      cooldown                 = step_scaling_policy_configuration.value["cooldown"]
      metric_aggregation_type  = step_scaling_policy_configuration.value["metric_aggregation_type"]
      min_adjustment_magnitude = step_scaling_policy_configuration.value["min_adjustment_magnitude"]

      dynamic "step_adjustment" {
        for_each = step_scaling_policy_configuration.value.step_adjustment
        content {
          metric_interval_lower_bound = step_adjustment.value["metric_interval_lower_bound"]
          metric_interval_upper_bound = step_adjustment.value["metric_interval_upper_bound"]
          scaling_adjustment          = step_adjustment.value["scaling_adjustment"]
        }
      }

    }
  }

  dynamic "target_tracking_scaling_policy_configuration" {
    for_each = var.target_tracking_scaling_policy_configuration
    content {
      disable_scale_in   = target_tracking_scaling_policy_configuration.value["disable_scale_in"]
      scale_in_cooldown  = target_tracking_scaling_policy_configuration.value["scale_in_cooldown"]
      scale_out_cooldown = target_tracking_scaling_policy_configuration.value["scale_out_cooldown"]
      target_value       = target_tracking_scaling_policy_configuration.value["target_value"]

      dynamic "customized_metric_specification" {
        for_each = target_tracking_scaling_policy_configuration.value.customized_metric_specification
        content {
          metric_name = customized_metric_specification.value["metric_name"]
          namespace   = customized_metric_specification.value["namespace"]
          statistic   = customized_metric_specification.value["statistic"]
          unit        = customized_metric_specification.value["unit"]

          dynamic "dimensions" {
            for_each = customized_metric_specification.value.dimensions
            content {
              name  = dimensions.value["name"]
              value = dimensions.value["value"]
            }
          }

        }
      }

      dynamic "predefined_metric_specification" {
        for_each = target_tracking_scaling_policy_configuration.value.predefined_metric_specification
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

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_appautoscaling_policy.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_appautoscaling_policy.this.id
}

output "this" {
  value = aws_appautoscaling_policy.this
}
```

[top](#index)