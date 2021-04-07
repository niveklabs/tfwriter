# tencentcloud_as_lifecycle_hook

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
module "tencentcloud_as_lifecycle_hook" {
  source = "./modules/tencentcloud/r/tencentcloud_as_lifecycle_hook"

  # default_result - (optional) is a type of string
  default_result = null
  # heartbeat_timeout - (optional) is a type of number
  heartbeat_timeout = null
  # lifecycle_hook_name - (required) is a type of string
  lifecycle_hook_name = null
  # lifecycle_transition - (required) is a type of string
  lifecycle_transition = null
  # notification_metadata - (optional) is a type of string
  notification_metadata = null
  # notification_queue_name - (optional) is a type of string
  notification_queue_name = null
  # notification_target_type - (optional) is a type of string
  notification_target_type = null
  # notification_topic_name - (optional) is a type of string
  notification_topic_name = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "default_result" {
  description = "(optional) - Defines the action the AS group should take when the lifecycle hook timeout elapses or if an unexpected failure occurs. Valid values: `CONTINUE` and `ABANDON`. The default value is `CONTINUE`."
  type        = string
  default     = null
}

variable "heartbeat_timeout" {
  description = "(optional) - Defines the amount of time, in seconds, that can elapse before the lifecycle hook times out. Valid value ranges: (30~3600). and default value is `300`."
  type        = number
  default     = null
}

variable "lifecycle_hook_name" {
  description = "(required) - The name of the lifecycle hook."
  type        = string
}

variable "lifecycle_transition" {
  description = "(required) - The instance state to which you want to attach the lifecycle hook. Valid values: `INSTANCE_LAUNCHING` and `INSTANCE_TERMINATING`."
  type        = string
}

variable "notification_metadata" {
  description = "(optional) - Contains additional information that you want to include any time AS sends a message to the notification target."
  type        = string
  default     = null
}

variable "notification_queue_name" {
  description = "(optional) - For CMQ_QUEUE type, a name of queue must be set."
  type        = string
  default     = null
}

variable "notification_target_type" {
  description = "(optional) - Target type. Valid values: `CMQ_QUEUE`, `CMQ_TOPIC`."
  type        = string
  default     = null
}

variable "notification_topic_name" {
  description = "(optional) - For CMQ_TOPIC type, a name of topic must be set."
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(required) - ID of a scaling group."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_as_lifecycle_hook" "this" {
  # default_result - (optional) is a type of string
  default_result = var.default_result
  # heartbeat_timeout - (optional) is a type of number
  heartbeat_timeout = var.heartbeat_timeout
  # lifecycle_hook_name - (required) is a type of string
  lifecycle_hook_name = var.lifecycle_hook_name
  # lifecycle_transition - (required) is a type of string
  lifecycle_transition = var.lifecycle_transition
  # notification_metadata - (optional) is a type of string
  notification_metadata = var.notification_metadata
  # notification_queue_name - (optional) is a type of string
  notification_queue_name = var.notification_queue_name
  # notification_target_type - (optional) is a type of string
  notification_target_type = var.notification_target_type
  # notification_topic_name - (optional) is a type of string
  notification_topic_name = var.notification_topic_name
  # scaling_group_id - (required) is a type of string
  scaling_group_id = var.scaling_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_as_lifecycle_hook.this.id
}

output "this" {
  value = tencentcloud_as_lifecycle_hook.this
}
```

[top](#index)