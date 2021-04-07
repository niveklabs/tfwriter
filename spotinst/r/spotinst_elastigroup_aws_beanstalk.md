# spotinst_elastigroup_aws_beanstalk

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_elastigroup_aws_beanstalk" {
  source = "./modules/spotinst/r/spotinst_elastigroup_aws_beanstalk"

  # beanstalk_environment_id - (optional) is a type of string
  beanstalk_environment_id = null
  # beanstalk_environment_name - (optional) is a type of string
  beanstalk_environment_name = null
  # desired_capacity - (required) is a type of number
  desired_capacity = null
  # instance_types_spot - (required) is a type of list of string
  instance_types_spot = []
  # maintenance - (optional) is a type of string
  maintenance = null
  # max_size - (required) is a type of number
  max_size = null
  # min_size - (required) is a type of number
  min_size = null
  # name - (required) is a type of string
  name = null
  # product - (required) is a type of string
  product = null
  # region - (required) is a type of string
  region = null

  deployment_preferences = [{
    automatic_roll        = null
    batch_size_percentage = null
    grace_period          = null
    strategy = [{
      action                 = null
      should_drain_instances = null
    }]
  }]

  managed_actions = [{
    platform_update = [{
      perform_at   = null
      time_window  = null
      update_level = null
    }]
  }]

  scheduled_task = [{
    adjustment            = null
    adjustment_percentage = null
    batch_size_percentage = null
    cron_expression       = null
    frequency             = null
    grace_period          = null
    is_enabled            = null
    max_capacity          = null
    min_capacity          = null
    scale_max_capacity    = null
    scale_min_capacity    = null
    scale_target_capacity = null
    start_time            = null
    target_capacity       = null
    task_type             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "beanstalk_environment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "beanstalk_environment_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_capacity" {
  description = "(required)"
  type        = number
}

variable "instance_types_spot" {
  description = "(required)"
  type        = list(string)
}

variable "maintenance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_size" {
  description = "(required)"
  type        = number
}

variable "min_size" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "product" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "deployment_preferences" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      automatic_roll        = bool
      batch_size_percentage = number
      grace_period          = number
      strategy = list(object(
        {
          action                 = string
          should_drain_instances = bool
        }
      ))
    }
  ))
  default = []
}

variable "managed_actions" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      platform_update = list(object(
        {
          perform_at   = string
          time_window  = string
          update_level = string
        }
      ))
    }
  ))
  default = []
}

variable "scheduled_task" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      adjustment            = string
      adjustment_percentage = string
      batch_size_percentage = string
      cron_expression       = string
      frequency             = string
      grace_period          = string
      is_enabled            = bool
      max_capacity          = string
      min_capacity          = string
      scale_max_capacity    = string
      scale_min_capacity    = string
      scale_target_capacity = string
      start_time            = string
      target_capacity       = string
      task_type             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_elastigroup_aws_beanstalk" "this" {
  # beanstalk_environment_id - (optional) is a type of string
  beanstalk_environment_id = var.beanstalk_environment_id
  # beanstalk_environment_name - (optional) is a type of string
  beanstalk_environment_name = var.beanstalk_environment_name
  # desired_capacity - (required) is a type of number
  desired_capacity = var.desired_capacity
  # instance_types_spot - (required) is a type of list of string
  instance_types_spot = var.instance_types_spot
  # maintenance - (optional) is a type of string
  maintenance = var.maintenance
  # max_size - (required) is a type of number
  max_size = var.max_size
  # min_size - (required) is a type of number
  min_size = var.min_size
  # name - (required) is a type of string
  name = var.name
  # product - (required) is a type of string
  product = var.product
  # region - (required) is a type of string
  region = var.region

  dynamic "deployment_preferences" {
    for_each = var.deployment_preferences
    content {
      # automatic_roll - (optional) is a type of bool
      automatic_roll = deployment_preferences.value["automatic_roll"]
      # batch_size_percentage - (optional) is a type of number
      batch_size_percentage = deployment_preferences.value["batch_size_percentage"]
      # grace_period - (optional) is a type of number
      grace_period = deployment_preferences.value["grace_period"]

      dynamic "strategy" {
        for_each = deployment_preferences.value.strategy
        content {
          # action - (optional) is a type of string
          action = strategy.value["action"]
          # should_drain_instances - (optional) is a type of bool
          should_drain_instances = strategy.value["should_drain_instances"]
        }
      }

    }
  }

  dynamic "managed_actions" {
    for_each = var.managed_actions
    content {

      dynamic "platform_update" {
        for_each = managed_actions.value.platform_update
        content {
          # perform_at - (optional) is a type of string
          perform_at = platform_update.value["perform_at"]
          # time_window - (optional) is a type of string
          time_window = platform_update.value["time_window"]
          # update_level - (optional) is a type of string
          update_level = platform_update.value["update_level"]
        }
      }

    }
  }

  dynamic "scheduled_task" {
    for_each = var.scheduled_task
    content {
      # adjustment - (optional) is a type of string
      adjustment = scheduled_task.value["adjustment"]
      # adjustment_percentage - (optional) is a type of string
      adjustment_percentage = scheduled_task.value["adjustment_percentage"]
      # batch_size_percentage - (optional) is a type of string
      batch_size_percentage = scheduled_task.value["batch_size_percentage"]
      # cron_expression - (optional) is a type of string
      cron_expression = scheduled_task.value["cron_expression"]
      # frequency - (optional) is a type of string
      frequency = scheduled_task.value["frequency"]
      # grace_period - (optional) is a type of string
      grace_period = scheduled_task.value["grace_period"]
      # is_enabled - (optional) is a type of bool
      is_enabled = scheduled_task.value["is_enabled"]
      # max_capacity - (optional) is a type of string
      max_capacity = scheduled_task.value["max_capacity"]
      # min_capacity - (optional) is a type of string
      min_capacity = scheduled_task.value["min_capacity"]
      # scale_max_capacity - (optional) is a type of string
      scale_max_capacity = scheduled_task.value["scale_max_capacity"]
      # scale_min_capacity - (optional) is a type of string
      scale_min_capacity = scheduled_task.value["scale_min_capacity"]
      # scale_target_capacity - (optional) is a type of string
      scale_target_capacity = scheduled_task.value["scale_target_capacity"]
      # start_time - (optional) is a type of string
      start_time = scheduled_task.value["start_time"]
      # target_capacity - (optional) is a type of string
      target_capacity = scheduled_task.value["target_capacity"]
      # task_type - (required) is a type of string
      task_type = scheduled_task.value["task_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_elastigroup_aws_beanstalk.this.id
}

output "this" {
  value = spotinst_elastigroup_aws_beanstalk.this
}
```

[top](#index)