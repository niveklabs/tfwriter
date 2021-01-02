# aws_codedeploy_deployment_group

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
module "aws_codedeploy_deployment_group" {
  source = "./modules/aws/r/aws_codedeploy_deployment_group"

  # app_name - (required) is a type of string
  app_name = null
  # autoscaling_groups - (optional) is a type of set of string
  autoscaling_groups = []
  # deployment_config_name - (optional) is a type of string
  deployment_config_name = null
  # deployment_group_name - (required) is a type of string
  deployment_group_name = null
  # service_role_arn - (required) is a type of string
  service_role_arn = null

  alarm_configuration = [{
    alarms                    = []
    enabled                   = null
    ignore_poll_alarm_failure = null
  }]

  auto_rollback_configuration = [{
    enabled = null
    events  = []
  }]

  blue_green_deployment_config = [{
    deployment_ready_option = [{
      action_on_timeout    = null
      wait_time_in_minutes = null
    }]
    green_fleet_provisioning_option = [{
      action = null
    }]
    terminate_blue_instances_on_deployment_success = [{
      action                           = null
      termination_wait_time_in_minutes = null
    }]
  }]

  deployment_style = [{
    deployment_option = null
    deployment_type   = null
  }]

  ec2_tag_filter = [{
    key   = null
    type  = null
    value = null
  }]

  ec2_tag_set = [{
    ec2_tag_filter = [{
      key   = null
      type  = null
      value = null
    }]
  }]

  ecs_service = [{
    cluster_name = null
    service_name = null
  }]

  load_balancer_info = [{
    elb_info = [{
      name = null
    }]
    target_group_info = [{
      name = null
    }]
    target_group_pair_info = [{
      prod_traffic_route = [{
        listener_arns = []
      }]
      target_group = [{
        name = null
      }]
      test_traffic_route = [{
        listener_arns = []
      }]
    }]
  }]

  on_premises_instance_tag_filter = [{
    key   = null
    type  = null
    value = null
  }]

  trigger_configuration = [{
    trigger_events     = []
    trigger_name       = null
    trigger_target_arn = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_name" {
  description = "(required)"
  type        = string
}

variable "autoscaling_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "deployment_config_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_group_name" {
  description = "(required)"
  type        = string
}

variable "service_role_arn" {
  description = "(required)"
  type        = string
}

variable "alarm_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      alarms                    = set(string)
      enabled                   = bool
      ignore_poll_alarm_failure = bool
    }
  ))
  default = []
}

variable "auto_rollback_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
      events  = set(string)
    }
  ))
  default = []
}

variable "blue_green_deployment_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      deployment_ready_option = list(object(
        {
          action_on_timeout    = string
          wait_time_in_minutes = number
        }
      ))
      green_fleet_provisioning_option = list(object(
        {
          action = string
        }
      ))
      terminate_blue_instances_on_deployment_success = list(object(
        {
          action                           = string
          termination_wait_time_in_minutes = number
        }
      ))
    }
  ))
  default = []
}

variable "deployment_style" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      deployment_option = string
      deployment_type   = string
    }
  ))
  default = []
}

variable "ec2_tag_filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      type  = string
      value = string
    }
  ))
  default = []
}

variable "ec2_tag_set" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ec2_tag_filter = set(object(
        {
          key   = string
          type  = string
          value = string
        }
      ))
    }
  ))
  default = []
}

variable "ecs_service" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cluster_name = string
      service_name = string
    }
  ))
  default = []
}

variable "load_balancer_info" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      elb_info = set(object(
        {
          name = string
        }
      ))
      target_group_info = set(object(
        {
          name = string
        }
      ))
      target_group_pair_info = list(object(
        {
          prod_traffic_route = list(object(
            {
              listener_arns = set(string)
            }
          ))
          target_group = list(object(
            {
              name = string
            }
          ))
          test_traffic_route = list(object(
            {
              listener_arns = set(string)
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "on_premises_instance_tag_filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      type  = string
      value = string
    }
  ))
  default = []
}

variable "trigger_configuration" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      trigger_events     = set(string)
      trigger_name       = string
      trigger_target_arn = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_codedeploy_deployment_group" "this" {
  app_name               = var.app_name
  autoscaling_groups     = var.autoscaling_groups
  deployment_config_name = var.deployment_config_name
  deployment_group_name  = var.deployment_group_name
  service_role_arn       = var.service_role_arn

  dynamic "alarm_configuration" {
    for_each = var.alarm_configuration
    content {
      alarms                    = alarm_configuration.value["alarms"]
      enabled                   = alarm_configuration.value["enabled"]
      ignore_poll_alarm_failure = alarm_configuration.value["ignore_poll_alarm_failure"]
    }
  }

  dynamic "auto_rollback_configuration" {
    for_each = var.auto_rollback_configuration
    content {
      enabled = auto_rollback_configuration.value["enabled"]
      events  = auto_rollback_configuration.value["events"]
    }
  }

  dynamic "blue_green_deployment_config" {
    for_each = var.blue_green_deployment_config
    content {

      dynamic "deployment_ready_option" {
        for_each = blue_green_deployment_config.value.deployment_ready_option
        content {
          action_on_timeout    = deployment_ready_option.value["action_on_timeout"]
          wait_time_in_minutes = deployment_ready_option.value["wait_time_in_minutes"]
        }
      }

      dynamic "green_fleet_provisioning_option" {
        for_each = blue_green_deployment_config.value.green_fleet_provisioning_option
        content {
          action = green_fleet_provisioning_option.value["action"]
        }
      }

      dynamic "terminate_blue_instances_on_deployment_success" {
        for_each = blue_green_deployment_config.value.terminate_blue_instances_on_deployment_success
        content {
          action                           = terminate_blue_instances_on_deployment_success.value["action"]
          termination_wait_time_in_minutes = terminate_blue_instances_on_deployment_success.value["termination_wait_time_in_minutes"]
        }
      }

    }
  }

  dynamic "deployment_style" {
    for_each = var.deployment_style
    content {
      deployment_option = deployment_style.value["deployment_option"]
      deployment_type   = deployment_style.value["deployment_type"]
    }
  }

  dynamic "ec2_tag_filter" {
    for_each = var.ec2_tag_filter
    content {
      key   = ec2_tag_filter.value["key"]
      type  = ec2_tag_filter.value["type"]
      value = ec2_tag_filter.value["value"]
    }
  }

  dynamic "ec2_tag_set" {
    for_each = var.ec2_tag_set
    content {

      dynamic "ec2_tag_filter" {
        for_each = ec2_tag_set.value.ec2_tag_filter
        content {
          key   = ec2_tag_filter.value["key"]
          type  = ec2_tag_filter.value["type"]
          value = ec2_tag_filter.value["value"]
        }
      }

    }
  }

  dynamic "ecs_service" {
    for_each = var.ecs_service
    content {
      cluster_name = ecs_service.value["cluster_name"]
      service_name = ecs_service.value["service_name"]
    }
  }

  dynamic "load_balancer_info" {
    for_each = var.load_balancer_info
    content {

      dynamic "elb_info" {
        for_each = load_balancer_info.value.elb_info
        content {
          name = elb_info.value["name"]
        }
      }

      dynamic "target_group_info" {
        for_each = load_balancer_info.value.target_group_info
        content {
          name = target_group_info.value["name"]
        }
      }

      dynamic "target_group_pair_info" {
        for_each = load_balancer_info.value.target_group_pair_info
        content {

          dynamic "prod_traffic_route" {
            for_each = target_group_pair_info.value.prod_traffic_route
            content {
              listener_arns = prod_traffic_route.value["listener_arns"]
            }
          }

          dynamic "target_group" {
            for_each = target_group_pair_info.value.target_group
            content {
              name = target_group.value["name"]
            }
          }

          dynamic "test_traffic_route" {
            for_each = target_group_pair_info.value.test_traffic_route
            content {
              listener_arns = test_traffic_route.value["listener_arns"]
            }
          }

        }
      }

    }
  }

  dynamic "on_premises_instance_tag_filter" {
    for_each = var.on_premises_instance_tag_filter
    content {
      key   = on_premises_instance_tag_filter.value["key"]
      type  = on_premises_instance_tag_filter.value["type"]
      value = on_premises_instance_tag_filter.value["value"]
    }
  }

  dynamic "trigger_configuration" {
    for_each = var.trigger_configuration
    content {
      trigger_events     = trigger_configuration.value["trigger_events"]
      trigger_name       = trigger_configuration.value["trigger_name"]
      trigger_target_arn = trigger_configuration.value["trigger_target_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_codedeploy_deployment_group.this.id
}

output "this" {
  value = aws_codedeploy_deployment_group.this
}
```

[top](#index)