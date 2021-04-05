# spotinst_ocean_ecs

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
module "spotinst_ocean_ecs" {
  source = "./modules/spotinst/r/spotinst_ocean_ecs"

  # associate_public_ip_address - (optional) is a type of bool
  associate_public_ip_address = null
  # cluster_name - (required) is a type of string
  cluster_name = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # draining_timeout - (optional) is a type of number
  draining_timeout = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = null
  # image_id - (optional) is a type of string
  image_id = null
  # key_pair - (optional) is a type of string
  key_pair = null
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # monitoring - (optional) is a type of bool
  monitoring = null
  # name - (required) is a type of string
  name = null
  # region - (required) is a type of string
  region = null
  # security_group_ids - (required) is a type of list of string
  security_group_ids = []
  # subnet_ids - (required) is a type of list of string
  subnet_ids = []
  # user_data - (optional) is a type of string
  user_data = null
  # utilize_reserved_instances - (optional) is a type of bool
  utilize_reserved_instances = null
  # whitelist - (optional) is a type of list of string
  whitelist = []

  autoscaler = [{
    cooldown = null
    down = [{
      max_scale_down_percentage = null
    }]
    headroom = [{
      cpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    is_auto_config = null
    is_enabled     = null
    resource_limits = [{
      max_memory_gib = null
      max_vcpu       = null
    }]
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

variable "cluster_name" {
  description = "(required)"
  type        = string
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

variable "key_pair" {
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
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "security_group_ids" {
  description = "(required)"
  type        = list(string)
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
      cooldown = number
      down = list(object(
        {
          max_scale_down_percentage = number
        }
      ))
      headroom = list(object(
        {
          cpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      is_auto_config = bool
      is_enabled     = bool
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
resource "spotinst_ocean_ecs" "this" {
  associate_public_ip_address = var.associate_public_ip_address
  cluster_name                = var.cluster_name
  desired_capacity            = var.desired_capacity
  draining_timeout            = var.draining_timeout
  ebs_optimized               = var.ebs_optimized
  iam_instance_profile        = var.iam_instance_profile
  image_id                    = var.image_id
  key_pair                    = var.key_pair
  max_size                    = var.max_size
  min_size                    = var.min_size
  monitoring                  = var.monitoring
  name                        = var.name
  region                      = var.region
  security_group_ids          = var.security_group_ids
  subnet_ids                  = var.subnet_ids
  user_data                   = var.user_data
  utilize_reserved_instances  = var.utilize_reserved_instances
  whitelist                   = var.whitelist

  dynamic "autoscaler" {
    for_each = var.autoscaler
    content {
      cooldown       = autoscaler.value["cooldown"]
      is_auto_config = autoscaler.value["is_auto_config"]
      is_enabled     = autoscaler.value["is_enabled"]

      dynamic "down" {
        for_each = autoscaler.value.down
        content {
          max_scale_down_percentage = down.value["max_scale_down_percentage"]
        }
      }

      dynamic "headroom" {
        for_each = autoscaler.value.headroom
        content {
          cpu_per_unit    = headroom.value["cpu_per_unit"]
          memory_per_unit = headroom.value["memory_per_unit"]
          num_of_units    = headroom.value["num_of_units"]
        }
      }

      dynamic "resource_limits" {
        for_each = autoscaler.value.resource_limits
        content {
          max_memory_gib = resource_limits.value["max_memory_gib"]
          max_vcpu       = resource_limits.value["max_vcpu"]
        }
      }

    }
  }

  dynamic "scheduled_task" {
    for_each = var.scheduled_task
    content {

      dynamic "shutdown_hours" {
        for_each = scheduled_task.value.shutdown_hours
        content {
          is_enabled   = shutdown_hours.value["is_enabled"]
          time_windows = shutdown_hours.value["time_windows"]
        }
      }

      dynamic "tasks" {
        for_each = scheduled_task.value.tasks
        content {
          cron_expression = tasks.value["cron_expression"]
          is_enabled      = tasks.value["is_enabled"]
          task_type       = tasks.value["task_type"]
        }
      }

    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      key   = tags.value["key"]
      value = tags.value["value"]
    }
  }

  dynamic "update_policy" {
    for_each = var.update_policy
    content {
      should_roll = update_policy.value["should_roll"]

      dynamic "roll_config" {
        for_each = update_policy.value.roll_config
        content {
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
  value       = spotinst_ocean_ecs.this.desired_capacity
}

output "id" {
  description = "returns a string"
  value       = spotinst_ocean_ecs.this.id
}

output "max_size" {
  description = "returns a number"
  value       = spotinst_ocean_ecs.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = spotinst_ocean_ecs.this.min_size
}

output "this" {
  value = spotinst_ocean_ecs.this
}
```

[top](#index)