# alicloud_ess_lifecycle_hook

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
module "alicloud_ess_lifecycle_hook" {
  source = "./modules/alicloud/r/alicloud_ess_lifecycle_hook"

  # default_result - (optional) is a type of string
  default_result = null
  # heartbeat_timeout - (optional) is a type of number
  heartbeat_timeout = null
  # lifecycle_transition - (required) is a type of string
  lifecycle_transition = null
  # name - (optional) is a type of string
  name = null
  # notification_arn - (optional) is a type of string
  notification_arn = null
  # notification_metadata - (optional) is a type of string
  notification_metadata = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
}
```

[top](#index)

### Variables

```terraform
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_lifecycle_hook" "this" {
  # default_result - (optional) is a type of string
  default_result = var.default_result
  # heartbeat_timeout - (optional) is a type of number
  heartbeat_timeout = var.heartbeat_timeout
  # lifecycle_transition - (required) is a type of string
  lifecycle_transition = var.lifecycle_transition
  # name - (optional) is a type of string
  name = var.name
  # notification_arn - (optional) is a type of string
  notification_arn = var.notification_arn
  # notification_metadata - (optional) is a type of string
  notification_metadata = var.notification_metadata
  # scaling_group_id - (required) is a type of string
  scaling_group_id = var.scaling_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ess_lifecycle_hook.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_ess_lifecycle_hook.this.name
}

output "notification_arn" {
  description = "returns a string"
  value       = alicloud_ess_lifecycle_hook.this.notification_arn
}

output "notification_metadata" {
  description = "returns a string"
  value       = alicloud_ess_lifecycle_hook.this.notification_metadata
}

output "this" {
  value = alicloud_ess_lifecycle_hook.this
}
```

[top](#index)