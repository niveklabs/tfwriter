# aws_autoscaling_group

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_autoscaling_group" {
  source = "./modules/aws/r/aws_autoscaling_group"

  # availability_zones - (optional) is a type of set of string
  availability_zones = []
  # capacity_rebalance - (optional) is a type of bool
  capacity_rebalance = null
  # default_cooldown - (optional) is a type of number
  default_cooldown = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # enabled_metrics - (optional) is a type of set of string
  enabled_metrics = []
  # force_delete - (optional) is a type of bool
  force_delete = null
  # health_check_grace_period - (optional) is a type of number
  health_check_grace_period = null
  # health_check_type - (optional) is a type of string
  health_check_type = null
  # launch_configuration - (optional) is a type of string
  launch_configuration = null
  # load_balancers - (optional) is a type of set of string
  load_balancers = []
  # max_instance_lifetime - (optional) is a type of number
  max_instance_lifetime = null
  # max_size - (required) is a type of number
  max_size = null
  # metrics_granularity - (optional) is a type of string
  metrics_granularity = null
  # min_elb_capacity - (optional) is a type of number
  min_elb_capacity = null
  # min_size - (required) is a type of number
  min_size = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # placement_group - (optional) is a type of string
  placement_group = null
  # protect_from_scale_in - (optional) is a type of bool
  protect_from_scale_in = null
  # service_linked_role_arn - (optional) is a type of string
  service_linked_role_arn = null
  # suspended_processes - (optional) is a type of set of string
  suspended_processes = []
  # tags - (optional) is a type of set of map of string
  tags = [{}]
  # target_group_arns - (optional) is a type of set of string
  target_group_arns = []
  # termination_policies - (optional) is a type of list of string
  termination_policies = []
  # vpc_zone_identifier - (optional) is a type of set of string
  vpc_zone_identifier = []
  # wait_for_capacity_timeout - (optional) is a type of string
  wait_for_capacity_timeout = null
  # wait_for_elb_capacity - (optional) is a type of number
  wait_for_elb_capacity = null

  initial_lifecycle_hook = [{
    default_result          = null
    heartbeat_timeout       = null
    lifecycle_transition    = null
    name                    = null
    notification_metadata   = null
    notification_target_arn = null
    role_arn                = null
  }]

  instance_refresh = [{
    preferences = [{
      instance_warmup        = null
      min_healthy_percentage = null
    }]
    strategy = null
    triggers = []
  }]

  launch_template = [{
    id      = null
    name    = null
    version = null
  }]

  mixed_instances_policy = [{
    instances_distribution = [{
      on_demand_allocation_strategy            = null
      on_demand_base_capacity                  = null
      on_demand_percentage_above_base_capacity = null
      spot_allocation_strategy                 = null
      spot_instance_pools                      = null
      spot_max_price                           = null
    }]
    launch_template = [{
      launch_template_specification = [{
        launch_template_id   = null
        launch_template_name = null
        version              = null
      }]
      override = [{
        instance_type = null
        launch_template_specification = [{
          launch_template_id   = null
          launch_template_name = null
          version              = null
        }]
        weighted_capacity = null
      }]
    }]
  }]

  tag = [{
    key                 = null
    propagate_at_launch = null
    value               = null
  }]

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zones" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "capacity_rebalance" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "default_cooldown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enabled_metrics" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "force_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "health_check_grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "launch_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "max_instance_lifetime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_size" {
  description = "(required)"
  type        = number
}

variable "metrics_granularity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_elb_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_size" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "placement_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protect_from_scale_in" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "service_linked_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suspended_processes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(map(string))
  default     = null
}

variable "target_group_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "termination_policies" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "vpc_zone_identifier" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "wait_for_capacity_timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_for_elb_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "initial_lifecycle_hook" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default_result          = string
      heartbeat_timeout       = number
      lifecycle_transition    = string
      name                    = string
      notification_metadata   = string
      notification_target_arn = string
      role_arn                = string
    }
  ))
  default = []
}

variable "instance_refresh" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      preferences = list(object(
        {
          instance_warmup        = string
          min_healthy_percentage = number
        }
      ))
      strategy = string
      triggers = set(string)
    }
  ))
  default = []
}

variable "launch_template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id      = string
      name    = string
      version = string
    }
  ))
  default = []
}

variable "mixed_instances_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      instances_distribution = list(object(
        {
          on_demand_allocation_strategy            = string
          on_demand_base_capacity                  = number
          on_demand_percentage_above_base_capacity = number
          spot_allocation_strategy                 = string
          spot_instance_pools                      = number
          spot_max_price                           = string
        }
      ))
      launch_template = list(object(
        {
          launch_template_specification = list(object(
            {
              launch_template_id   = string
              launch_template_name = string
              version              = string
            }
          ))
          override = list(object(
            {
              instance_type = string
              launch_template_specification = list(object(
                {
                  launch_template_id   = string
                  launch_template_name = string
                  version              = string
                }
              ))
              weighted_capacity = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key                 = string
      propagate_at_launch = bool
      value               = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_autoscaling_group" "this" {
  availability_zones        = var.availability_zones
  capacity_rebalance        = var.capacity_rebalance
  default_cooldown          = var.default_cooldown
  desired_capacity          = var.desired_capacity
  enabled_metrics           = var.enabled_metrics
  force_delete              = var.force_delete
  health_check_grace_period = var.health_check_grace_period
  health_check_type         = var.health_check_type
  launch_configuration      = var.launch_configuration
  load_balancers            = var.load_balancers
  max_instance_lifetime     = var.max_instance_lifetime
  max_size                  = var.max_size
  metrics_granularity       = var.metrics_granularity
  min_elb_capacity          = var.min_elb_capacity
  min_size                  = var.min_size
  name                      = var.name
  name_prefix               = var.name_prefix
  placement_group           = var.placement_group
  protect_from_scale_in     = var.protect_from_scale_in
  service_linked_role_arn   = var.service_linked_role_arn
  suspended_processes       = var.suspended_processes
  tags                      = var.tags
  target_group_arns         = var.target_group_arns
  termination_policies      = var.termination_policies
  vpc_zone_identifier       = var.vpc_zone_identifier
  wait_for_capacity_timeout = var.wait_for_capacity_timeout
  wait_for_elb_capacity     = var.wait_for_elb_capacity

  dynamic "initial_lifecycle_hook" {
    for_each = var.initial_lifecycle_hook
    content {
      default_result          = initial_lifecycle_hook.value["default_result"]
      heartbeat_timeout       = initial_lifecycle_hook.value["heartbeat_timeout"]
      lifecycle_transition    = initial_lifecycle_hook.value["lifecycle_transition"]
      name                    = initial_lifecycle_hook.value["name"]
      notification_metadata   = initial_lifecycle_hook.value["notification_metadata"]
      notification_target_arn = initial_lifecycle_hook.value["notification_target_arn"]
      role_arn                = initial_lifecycle_hook.value["role_arn"]
    }
  }

  dynamic "instance_refresh" {
    for_each = var.instance_refresh
    content {
      strategy = instance_refresh.value["strategy"]
      triggers = instance_refresh.value["triggers"]

      dynamic "preferences" {
        for_each = instance_refresh.value.preferences
        content {
          instance_warmup        = preferences.value["instance_warmup"]
          min_healthy_percentage = preferences.value["min_healthy_percentage"]
        }
      }

    }
  }

  dynamic "launch_template" {
    for_each = var.launch_template
    content {
      id      = launch_template.value["id"]
      name    = launch_template.value["name"]
      version = launch_template.value["version"]
    }
  }

  dynamic "mixed_instances_policy" {
    for_each = var.mixed_instances_policy
    content {

      dynamic "instances_distribution" {
        for_each = mixed_instances_policy.value.instances_distribution
        content {
          on_demand_allocation_strategy            = instances_distribution.value["on_demand_allocation_strategy"]
          on_demand_base_capacity                  = instances_distribution.value["on_demand_base_capacity"]
          on_demand_percentage_above_base_capacity = instances_distribution.value["on_demand_percentage_above_base_capacity"]
          spot_allocation_strategy                 = instances_distribution.value["spot_allocation_strategy"]
          spot_instance_pools                      = instances_distribution.value["spot_instance_pools"]
          spot_max_price                           = instances_distribution.value["spot_max_price"]
        }
      }

      dynamic "launch_template" {
        for_each = mixed_instances_policy.value.launch_template
        content {

          dynamic "launch_template_specification" {
            for_each = launch_template.value.launch_template_specification
            content {
              launch_template_id   = launch_template_specification.value["launch_template_id"]
              launch_template_name = launch_template_specification.value["launch_template_name"]
              version              = launch_template_specification.value["version"]
            }
          }

          dynamic "override" {
            for_each = launch_template.value.override
            content {
              instance_type     = override.value["instance_type"]
              weighted_capacity = override.value["weighted_capacity"]

              dynamic "launch_template_specification" {
                for_each = override.value.launch_template_specification
                content {
                  launch_template_id   = launch_template_specification.value["launch_template_id"]
                  launch_template_name = launch_template_specification.value["launch_template_name"]
                  version              = launch_template_specification.value["version"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      key                 = tag.value["key"]
      propagate_at_launch = tag.value["propagate_at_launch"]
      value               = tag.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_autoscaling_group.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = aws_autoscaling_group.this.availability_zones
}

output "default_cooldown" {
  description = "returns a number"
  value       = aws_autoscaling_group.this.default_cooldown
}

output "desired_capacity" {
  description = "returns a number"
  value       = aws_autoscaling_group.this.desired_capacity
}

output "health_check_type" {
  description = "returns a string"
  value       = aws_autoscaling_group.this.health_check_type
}

output "id" {
  description = "returns a string"
  value       = aws_autoscaling_group.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_autoscaling_group.this.name
}

output "service_linked_role_arn" {
  description = "returns a string"
  value       = aws_autoscaling_group.this.service_linked_role_arn
}

output "vpc_zone_identifier" {
  description = "returns a set of string"
  value       = aws_autoscaling_group.this.vpc_zone_identifier
}

output "this" {
  value = aws_autoscaling_group.this
}
```

[top](#index)