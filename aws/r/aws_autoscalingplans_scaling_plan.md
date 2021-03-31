# aws_autoscalingplans_scaling_plan

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_autoscalingplans_scaling_plan" {
  source = "./modules/aws/r/aws_autoscalingplans_scaling_plan"

  # name - (required) is a type of string
  name = null

  application_source = [{
    cloudformation_stack_arn = null
    tag_filter = [{
      key    = null
      values = []
    }]
  }]

  scaling_instruction = [{
    customized_load_metric_specification = [{
      dimensions  = {}
      metric_name = null
      namespace   = null
      statistic   = null
      unit        = null
    }]
    disable_dynamic_scaling = null
    max_capacity            = null
    min_capacity            = null
    predefined_load_metric_specification = [{
      predefined_load_metric_type = null
      resource_label              = null
    }]
    predictive_scaling_max_capacity_behavior = null
    predictive_scaling_max_capacity_buffer   = null
    predictive_scaling_mode                  = null
    resource_id                              = null
    scalable_dimension                       = null
    scaling_policy_update_behavior           = null
    scheduled_action_buffer_time             = null
    service_namespace                        = null
    target_tracking_configuration = [{
      customized_scaling_metric_specification = [{
        dimensions  = {}
        metric_name = null
        namespace   = null
        statistic   = null
        unit        = null
      }]
      disable_scale_in          = null
      estimated_instance_warmup = null
      predefined_scaling_metric_specification = [{
        predefined_scaling_metric_type = null
        resource_label                 = null
      }]
      scale_in_cooldown  = null
      scale_out_cooldown = null
      target_value       = null
    }]
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

variable "application_source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cloudformation_stack_arn = string
      tag_filter = set(object(
        {
          key    = string
          values = set(string)
        }
      ))
    }
  ))
}

variable "scaling_instruction" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      customized_load_metric_specification = list(object(
        {
          dimensions  = map(string)
          metric_name = string
          namespace   = string
          statistic   = string
          unit        = string
        }
      ))
      disable_dynamic_scaling = bool
      max_capacity            = number
      min_capacity            = number
      predefined_load_metric_specification = list(object(
        {
          predefined_load_metric_type = string
          resource_label              = string
        }
      ))
      predictive_scaling_max_capacity_behavior = string
      predictive_scaling_max_capacity_buffer   = number
      predictive_scaling_mode                  = string
      resource_id                              = string
      scalable_dimension                       = string
      scaling_policy_update_behavior           = string
      scheduled_action_buffer_time             = number
      service_namespace                        = string
      target_tracking_configuration = set(object(
        {
          customized_scaling_metric_specification = list(object(
            {
              dimensions  = map(string)
              metric_name = string
              namespace   = string
              statistic   = string
              unit        = string
            }
          ))
          disable_scale_in          = bool
          estimated_instance_warmup = number
          predefined_scaling_metric_specification = list(object(
            {
              predefined_scaling_metric_type = string
              resource_label                 = string
            }
          ))
          scale_in_cooldown  = number
          scale_out_cooldown = number
          target_value       = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_autoscalingplans_scaling_plan" "this" {
  name = var.name

  dynamic "application_source" {
    for_each = var.application_source
    content {
      cloudformation_stack_arn = application_source.value["cloudformation_stack_arn"]

      dynamic "tag_filter" {
        for_each = application_source.value.tag_filter
        content {
          key    = tag_filter.value["key"]
          values = tag_filter.value["values"]
        }
      }

    }
  }

  dynamic "scaling_instruction" {
    for_each = var.scaling_instruction
    content {
      disable_dynamic_scaling                  = scaling_instruction.value["disable_dynamic_scaling"]
      max_capacity                             = scaling_instruction.value["max_capacity"]
      min_capacity                             = scaling_instruction.value["min_capacity"]
      predictive_scaling_max_capacity_behavior = scaling_instruction.value["predictive_scaling_max_capacity_behavior"]
      predictive_scaling_max_capacity_buffer   = scaling_instruction.value["predictive_scaling_max_capacity_buffer"]
      predictive_scaling_mode                  = scaling_instruction.value["predictive_scaling_mode"]
      resource_id                              = scaling_instruction.value["resource_id"]
      scalable_dimension                       = scaling_instruction.value["scalable_dimension"]
      scaling_policy_update_behavior           = scaling_instruction.value["scaling_policy_update_behavior"]
      scheduled_action_buffer_time             = scaling_instruction.value["scheduled_action_buffer_time"]
      service_namespace                        = scaling_instruction.value["service_namespace"]

      dynamic "customized_load_metric_specification" {
        for_each = scaling_instruction.value.customized_load_metric_specification
        content {
          dimensions  = customized_load_metric_specification.value["dimensions"]
          metric_name = customized_load_metric_specification.value["metric_name"]
          namespace   = customized_load_metric_specification.value["namespace"]
          statistic   = customized_load_metric_specification.value["statistic"]
          unit        = customized_load_metric_specification.value["unit"]
        }
      }

      dynamic "predefined_load_metric_specification" {
        for_each = scaling_instruction.value.predefined_load_metric_specification
        content {
          predefined_load_metric_type = predefined_load_metric_specification.value["predefined_load_metric_type"]
          resource_label              = predefined_load_metric_specification.value["resource_label"]
        }
      }

      dynamic "target_tracking_configuration" {
        for_each = scaling_instruction.value.target_tracking_configuration
        content {
          disable_scale_in          = target_tracking_configuration.value["disable_scale_in"]
          estimated_instance_warmup = target_tracking_configuration.value["estimated_instance_warmup"]
          scale_in_cooldown         = target_tracking_configuration.value["scale_in_cooldown"]
          scale_out_cooldown        = target_tracking_configuration.value["scale_out_cooldown"]
          target_value              = target_tracking_configuration.value["target_value"]

          dynamic "customized_scaling_metric_specification" {
            for_each = target_tracking_configuration.value.customized_scaling_metric_specification
            content {
              dimensions  = customized_scaling_metric_specification.value["dimensions"]
              metric_name = customized_scaling_metric_specification.value["metric_name"]
              namespace   = customized_scaling_metric_specification.value["namespace"]
              statistic   = customized_scaling_metric_specification.value["statistic"]
              unit        = customized_scaling_metric_specification.value["unit"]
            }
          }

          dynamic "predefined_scaling_metric_specification" {
            for_each = target_tracking_configuration.value.predefined_scaling_metric_specification
            content {
              predefined_scaling_metric_type = predefined_scaling_metric_specification.value["predefined_scaling_metric_type"]
              resource_label                 = predefined_scaling_metric_specification.value["resource_label"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_autoscalingplans_scaling_plan.this.id
}

output "scaling_plan_version" {
  description = "returns a number"
  value       = aws_autoscalingplans_scaling_plan.this.scaling_plan_version
}

output "this" {
  value = aws_autoscalingplans_scaling_plan.this
}
```

[top](#index)