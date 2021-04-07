# tencentcloud_as_schedule

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
module "tencentcloud_as_schedule" {
  source = "./modules/tencentcloud/r/tencentcloud_as_schedule"

  # desired_capacity - (required) is a type of number
  desired_capacity = null
  # end_time - (optional) is a type of string
  end_time = null
  # max_size - (required) is a type of number
  max_size = null
  # min_size - (required) is a type of number
  min_size = null
  # recurrence - (optional) is a type of string
  recurrence = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
  # schedule_action_name - (required) is a type of string
  schedule_action_name = null
  # start_time - (required) is a type of string
  start_time = null
}
```

[top](#index)

### Variables

```terraform
variable "desired_capacity" {
  description = "(required) - The desired number of CVM instances that should be running in the group."
  type        = number
}

variable "end_time" {
  description = "(optional) - The time for this action to end, in \"YYYY-MM-DDThh:mm:ss+08:00\" format (UTC+8)."
  type        = string
  default     = null
}

variable "max_size" {
  description = "(required) - The maximum size for the Auto Scaling group."
  type        = number
}

variable "min_size" {
  description = "(required) - The minimum size for the Auto Scaling group."
  type        = number
}

variable "recurrence" {
  description = "(optional) - The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format. And this argument should be set with end_time together."
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(required) - ID of a scaling group."
  type        = string
}

variable "schedule_action_name" {
  description = "(required) - The name of this scaling action."
  type        = string
}

variable "start_time" {
  description = "(required) - The time for this action to start, in \"YYYY-MM-DDThh:mm:ss+08:00\" format (UTC+8)."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_as_schedule" "this" {
  # desired_capacity - (required) is a type of number
  desired_capacity = var.desired_capacity
  # end_time - (optional) is a type of string
  end_time = var.end_time
  # max_size - (required) is a type of number
  max_size = var.max_size
  # min_size - (required) is a type of number
  min_size = var.min_size
  # recurrence - (optional) is a type of string
  recurrence = var.recurrence
  # scaling_group_id - (required) is a type of string
  scaling_group_id = var.scaling_group_id
  # schedule_action_name - (required) is a type of string
  schedule_action_name = var.schedule_action_name
  # start_time - (required) is a type of string
  start_time = var.start_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_as_schedule.this.id
}

output "this" {
  value = tencentcloud_as_schedule.this
}
```

[top](#index)