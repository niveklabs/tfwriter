# alicloud_ess_scheduled_task

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
module "alicloud_ess_scheduled_task" {
  source = "./modules/alicloud/r/alicloud_ess_scheduled_task"

  # description - (optional) is a type of string
  description = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # launch_expiration_time - (optional) is a type of number
  launch_expiration_time = null
  # launch_time - (optional) is a type of string
  launch_time = null
  # max_value - (optional) is a type of number
  max_value = null
  # min_value - (optional) is a type of number
  min_value = null
  # recurrence_end_time - (optional) is a type of string
  recurrence_end_time = null
  # recurrence_type - (optional) is a type of string
  recurrence_type = null
  # recurrence_value - (optional) is a type of string
  recurrence_value = null
  # scaling_group_id - (optional) is a type of string
  scaling_group_id = null
  # scheduled_action - (optional) is a type of string
  scheduled_action = null
  # scheduled_task_name - (optional) is a type of string
  scheduled_task_name = null
  # task_enabled - (optional) is a type of bool
  task_enabled = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "launch_expiration_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "launch_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "recurrence_end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recurrence_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recurrence_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduled_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduled_task_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "task_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_scheduled_task" "this" {
  description            = var.description
  desired_capacity       = var.desired_capacity
  launch_expiration_time = var.launch_expiration_time
  launch_time            = var.launch_time
  max_value              = var.max_value
  min_value              = var.min_value
  recurrence_end_time    = var.recurrence_end_time
  recurrence_type        = var.recurrence_type
  recurrence_value       = var.recurrence_value
  scaling_group_id       = var.scaling_group_id
  scheduled_action       = var.scheduled_action
  scheduled_task_name    = var.scheduled_task_name
  task_enabled           = var.task_enabled
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = alicloud_ess_scheduled_task.this.description
}

output "id" {
  description = "returns a string"
  value       = alicloud_ess_scheduled_task.this.id
}

output "recurrence_end_time" {
  description = "returns a string"
  value       = alicloud_ess_scheduled_task.this.recurrence_end_time
}

output "recurrence_type" {
  description = "returns a string"
  value       = alicloud_ess_scheduled_task.this.recurrence_type
}

output "recurrence_value" {
  description = "returns a string"
  value       = alicloud_ess_scheduled_task.this.recurrence_value
}

output "scaling_group_id" {
  description = "returns a string"
  value       = alicloud_ess_scheduled_task.this.scaling_group_id
}

output "this" {
  value = alicloud_ess_scheduled_task.this
}
```

[top](#index)