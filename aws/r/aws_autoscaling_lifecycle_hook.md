# aws_autoscaling_lifecycle_hook

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
module "aws_autoscaling_lifecycle_hook" {
  source = "./modules/aws/r/aws_autoscaling_lifecycle_hook"

  # autoscaling_group_name - (required) is a type of string
  autoscaling_group_name = null
  # default_result - (optional) is a type of string
  default_result = null
  # heartbeat_timeout - (optional) is a type of number
  heartbeat_timeout = null
  # lifecycle_transition - (required) is a type of string
  lifecycle_transition = null
  # name - (required) is a type of string
  name = null
  # notification_metadata - (optional) is a type of string
  notification_metadata = null
  # notification_target_arn - (optional) is a type of string
  notification_target_arn = null
  # role_arn - (optional) is a type of string
  role_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "autoscaling_group_name" {
  description = "(required)"
  type        = string
}

variable "default_result" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "heartbeat_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lifecycle_transition" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_target_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_autoscaling_lifecycle_hook" "this" {
  autoscaling_group_name  = var.autoscaling_group_name
  default_result          = var.default_result
  heartbeat_timeout       = var.heartbeat_timeout
  lifecycle_transition    = var.lifecycle_transition
  name                    = var.name
  notification_metadata   = var.notification_metadata
  notification_target_arn = var.notification_target_arn
  role_arn                = var.role_arn
}
```

[top](#index)

### Outputs

```terraform
output "default_result" {
  description = "returns a string"
  value       = aws_autoscaling_lifecycle_hook.this.default_result
}

output "id" {
  description = "returns a string"
  value       = aws_autoscaling_lifecycle_hook.this.id
}

output "this" {
  value = aws_autoscaling_lifecycle_hook.this
}
```

[top](#index)