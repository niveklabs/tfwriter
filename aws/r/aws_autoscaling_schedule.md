# aws_autoscaling_schedule

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
module "aws_autoscaling_schedule" {
  source = "./modules/aws/r/aws_autoscaling_schedule"

  # autoscaling_group_name - (required) is a type of string
  autoscaling_group_name = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # end_time - (optional) is a type of string
  end_time = null
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # recurrence - (optional) is a type of string
  recurrence = null
  # scheduled_action_name - (required) is a type of string
  scheduled_action_name = null
  # start_time - (optional) is a type of string
  start_time = null
}
```

[top](#index)

### Variables

```terraform
variable "autoscaling_group_name" {
  description = "(required)"
  type        = string
}

variable "desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "end_time" {
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

variable "recurrence" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduled_action_name" {
  description = "(required)"
  type        = string
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_autoscaling_schedule" "this" {
  autoscaling_group_name = var.autoscaling_group_name
  desired_capacity       = var.desired_capacity
  end_time               = var.end_time
  max_size               = var.max_size
  min_size               = var.min_size
  recurrence             = var.recurrence
  scheduled_action_name  = var.scheduled_action_name
  start_time             = var.start_time
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_autoscaling_schedule.this.arn
}

output "desired_capacity" {
  description = "returns a number"
  value       = aws_autoscaling_schedule.this.desired_capacity
}

output "end_time" {
  description = "returns a string"
  value       = aws_autoscaling_schedule.this.end_time
}

output "id" {
  description = "returns a string"
  value       = aws_autoscaling_schedule.this.id
}

output "max_size" {
  description = "returns a number"
  value       = aws_autoscaling_schedule.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = aws_autoscaling_schedule.this.min_size
}

output "recurrence" {
  description = "returns a string"
  value       = aws_autoscaling_schedule.this.recurrence
}

output "start_time" {
  description = "returns a string"
  value       = aws_autoscaling_schedule.this.start_time
}

output "this" {
  value = aws_autoscaling_schedule.this
}
```

[top](#index)