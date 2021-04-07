# spotinst_ocean_aws

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
module "spotinst_ocean_aws" {
  source = "./modules/spotinst/r/spotinst_ocean_aws"

  # associate_public_ip_address - (optional) is a type of bool
  associate_public_ip_address = null
  # blacklist - (optional) is a type of list of string
  blacklist = []
  # controller_id - (optional) is a type of string
  controller_id = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # draining_timeout - (optional) is a type of number
  draining_timeout = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # fallback_to_ondemand - (optional) is a type of bool
  fallback_to_ondemand = null
  # grace_period - (optional) is a type of number
  grace_period = null
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = null
  # image_id - (optional) is a type of string
  image_id = null
  # key_name - (optional) is a type of string
  key_name = null
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # monitoring - (optional) is a type of bool
  monitoring = null
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # root_volume_size - (optional) is a type of number
  root_volume_size = null
  # security_groups - (required) is a type of list of string
  security_groups = []
  # spot_percentage - (optional) is a type of number
  spot_percentage = null
  # subnet_ids - (required) is a type of list of string
  subnet_ids = []
  # user_data - (optional) is a type of string
  user_data = null
  # utilize_reserved_instances - (optional) is a type of bool
  utilize_reserved_instances = null
  # whitelist - (optional) is a type of list of string
  whitelist = []

  autoscaler = [{
    auto_headroom_percentage = null
    autoscale_cooldown       = null
    autoscale_down = [{
      evaluation_periods        = null
      max_scale_down_percentage = null
    }]
    autoscale_headroom = [{
      cpu_per_unit    = null
      gpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    autoscale_is_auto_config = null
    autoscale_is_enabled     = null
    resource_limits = [{
      max_memory_gib = null
      max_vcpu       = null
    }]
  }]

  load_balancers = [{
    arn  = null
    name = null
    type = null
  }]

  scheduled_task = [{
    shutdown_hours = [{
      is_enabled   = null
      time_windows = []
    }]
    tasks = [{
      cron_expression = null
      is_enabled      = null
      task_type       = null
    }]
  }]

  tags = [{
    key   = null
    value = null
  }]

  update_policy = [{
    roll_config = [{
      batch_size_percentage = null
    }]
    should_roll = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "associate_public_ip_address" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "blacklist" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "controller_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "draining_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "fallback_to_ondemand" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iam_instance_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitoring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "root_volume_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_groups" {
  description = "(required)"
  type        = list(string)
}

variable "spot_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = list(string)
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "utilize_reserved_instances" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "whitelist" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "autoscaler" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_headroom_percentage = number
      autoscale_cooldown       = number
      autoscale_down = list(object(
        {
          evaluation_periods        = number
          max_scale_down_percentage = number
        }
      ))
      autoscale_headroom = list(object(
        {
          cpu_per_unit    = number
          gpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      autoscale_is_auto_config = bool
      autoscale_is_enabled     = bool
      resource_limits = list(object(
        {
          max_memory_gib = number
          max_vcpu       = number
        }
      ))
    }
  ))
  default = []
}

variable "load_balancers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      arn  = string
      name = string
      type = string
    }
  ))
  default = []
}

variable "scheduled_task" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      shutdown_hours = list(object(
        {
          is_enabled   = bool
          time_windows = list(string)
        }
      ))
      tasks = list(object(
        {
          cron_expression = string
          is_enabled      = bool
          task_type       = string
        }
      ))
    }
  ))
  default = []
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "update_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      roll_config = list(object(
        {
          batch_size_percentage = number
        }
      ))
      should_roll = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_ocean_aws" "this" {
  # associate_public_ip_address - (optional) is a type of bool
  associate_public_ip_address = var.associate_public_ip_address
  # blacklist - (optional) is a type of list of string
  blacklist = var.blacklist
  # controller_id - (optional) is a type of string
  controller_id = var.controller_id
  # desired_capacity - (optional) is a type of number
  desired_capacity = var.desired_capacity
  # draining_timeout - (optional) is a type of number
  draining_timeout = var.draining_timeout
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = var.ebs_optimized
  # fallback_to_ondemand - (optional) is a type of bool
  fallback_to_ondemand = var.fallback_to_ondemand
  # grace_period - (optional) is a type of number
  grace_period = var.grace_period
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = var.iam_instance_profile
  # image_id - (optional) is a type of string
  image_id = var.image_id
  # key_name - (optional) is a type of string
  key_name = var.key_name
  # max_size - (optional) is a type of number
  max_size = var.max_size
  # min_size - (optional) is a type of number
  min_size = var.min_size
  # monitoring - (optional) is a type of bool
  monitoring = var.monitoring
  # name - (optional) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region
  # root_volume_size - (optional) is a type of number
  root_volume_size = var.root_volume_size
  # security_groups - (required) is a type of list of string
  security_groups = var.security_groups
  # spot_percentage - (optional) is a type of number
  spot_percentage = var.spot_percentage
  # subnet_ids - (required) is a type of list of string
  subnet_ids = var.subnet_ids
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # utilize_reserved_instances - (optional) is a type of bool
  utilize_reserved_instances = var.utilize_reserved_instances
  # whitelist - (optional) is a type of list of string
  whitelist = var.whitelist

  dynamic "autoscaler" {
    for_each = var.autoscaler
    content {
      # auto_headroom_percentage - (optional) is a type of number
      auto_headroom_percentage = autoscaler.value["auto_headroom_percentage"]
      # autoscale_cooldown - (optional) is a type of number
      autoscale_cooldown = autoscaler.value["autoscale_cooldown"]
      # autoscale_is_auto_config - (optional) is a type of bool
      autoscale_is_auto_config = autoscaler.value["autoscale_is_auto_config"]
      # autoscale_is_enabled - (optional) is a type of bool
      autoscale_is_enabled = autoscaler.value["autoscale_is_enabled"]

      dynamic "autoscale_down" {
        for_each = autoscaler.value.autoscale_down
        content {
          # evaluation_periods - (optional) is a type of number
          evaluation_periods = autoscale_down.value["evaluation_periods"]
          # max_scale_down_percentage - (optional) is a type of number
          max_scale_down_percentage = autoscale_down.value["max_scale_down_percentage"]
        }
      }

      dynamic "autoscale_headroom" {
        for_each = autoscaler.value.autoscale_headroom
        content {
          # cpu_per_unit - (optional) is a type of number
          cpu_per_unit = autoscale_headroom.value["cpu_per_unit"]
          # gpu_per_unit - (optional) is a type of number
          gpu_per_unit = autoscale_headroom.value["gpu_per_unit"]
          # memory_per_unit - (optional) is a type of number
          memory_per_unit = autoscale_headroom.value["memory_per_unit"]
          # num_of_units - (optional) is a type of number
          num_of_units = autoscale_headroom.value["num_of_units"]
        }
      }

      dynamic "resource_limits" {
        for_each = autoscaler.value.resource_limits
        content {
          # max_memory_gib - (optional) is a type of number
          max_memory_gib = resource_limits.value["max_memory_gib"]
          # max_vcpu - (optional) is a type of number
          max_vcpu = resource_limits.value["max_vcpu"]
        }
      }

    }
  }

  dynamic "load_balancers" {
    for_each = var.load_balancers
    content {
      # arn - (optional) is a type of string
      arn = load_balancers.value["arn"]
      # name - (optional) is a type of string
      name = load_balancers.value["name"]
      # type - (optional) is a type of string
      type = load_balancers.value["type"]
    }
  }

  dynamic "scheduled_task" {
    for_each = var.scheduled_task
    content {

      dynamic "shutdown_hours" {
        for_each = scheduled_task.value.shutdown_hours
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = shutdown_hours.value["is_enabled"]
          # time_windows - (required) is a type of list of string
          time_windows = shutdown_hours.value["time_windows"]
        }
      }

      dynamic "tasks" {
        for_each = scheduled_task.value.tasks
        content {
          # cron_expression - (required) is a type of string
          cron_expression = tasks.value["cron_expression"]
          # is_enabled - (required) is a type of bool
          is_enabled = tasks.value["is_enabled"]
          # task_type - (required) is a type of string
          task_type = tasks.value["task_type"]
        }
      }

    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

  dynamic "update_policy" {
    for_each = var.update_policy
    content {
      # should_roll - (required) is a type of bool
      should_roll = update_policy.value["should_roll"]

      dynamic "roll_config" {
        for_each = update_policy.value.roll_config
        content {
          # batch_size_percentage - (required) is a type of number
          batch_size_percentage = roll_config.value["batch_size_percentage"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "desired_capacity" {
  description = "returns a number"
  value       = spotinst_ocean_aws.this.desired_capacity
}

output "id" {
  description = "returns a string"
  value       = spotinst_ocean_aws.this.id
}

output "min_size" {
  description = "returns a number"
  value       = spotinst_ocean_aws.this.min_size
}

output "this" {
  value = spotinst_ocean_aws.this
}
```

[top](#index)