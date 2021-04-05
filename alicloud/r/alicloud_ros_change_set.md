# alicloud_ros_change_set

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
module "alicloud_ros_change_set" {
  source = "./modules/alicloud/r/alicloud_ros_change_set"

  # change_set_name - (required) is a type of string
  change_set_name = null
  # change_set_type - (optional) is a type of string
  change_set_type = null
  # description - (optional) is a type of string
  description = null
  # disable_rollback - (optional) is a type of bool
  disable_rollback = null
  # notification_urls - (optional) is a type of set of string
  notification_urls = []
  # ram_role_name - (optional) is a type of string
  ram_role_name = null
  # replacement_option - (optional) is a type of string
  replacement_option = null
  # stack_id - (optional) is a type of string
  stack_id = null
  # stack_name - (optional) is a type of string
  stack_name = null
  # stack_policy_body - (optional) is a type of string
  stack_policy_body = null
  # stack_policy_during_update_body - (optional) is a type of string
  stack_policy_during_update_body = null
  # stack_policy_during_update_url - (optional) is a type of string
  stack_policy_during_update_url = null
  # stack_policy_url - (optional) is a type of string
  stack_policy_url = null
  # template_body - (optional) is a type of string
  template_body = null
  # template_url - (optional) is a type of string
  template_url = null
  # timeout_in_minutes - (optional) is a type of number
  timeout_in_minutes = null
  # use_previous_parameters - (optional) is a type of bool
  use_previous_parameters = null

  parameters = [{
    parameter_key   = null
    parameter_value = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "change_set_name" {
  description = "(required)"
  type        = string
}

variable "change_set_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_rollback" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "notification_urls" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "ram_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replacement_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_policy_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_policy_during_update_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_policy_during_update_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_policy_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_previous_parameters" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      parameter_key   = string
      parameter_value = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ros_change_set" "this" {
  change_set_name                 = var.change_set_name
  change_set_type                 = var.change_set_type
  description                     = var.description
  disable_rollback                = var.disable_rollback
  notification_urls               = var.notification_urls
  ram_role_name                   = var.ram_role_name
  replacement_option              = var.replacement_option
  stack_id                        = var.stack_id
  stack_name                      = var.stack_name
  stack_policy_body               = var.stack_policy_body
  stack_policy_during_update_body = var.stack_policy_during_update_body
  stack_policy_during_update_url  = var.stack_policy_during_update_url
  stack_policy_url                = var.stack_policy_url
  template_body                   = var.template_body
  template_url                    = var.template_url
  timeout_in_minutes              = var.timeout_in_minutes
  use_previous_parameters         = var.use_previous_parameters

  dynamic "parameters" {
    for_each = var.parameters
    content {
      parameter_key   = parameters.value["parameter_key"]
      parameter_value = parameters.value["parameter_value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ros_change_set.this.id
}

output "stack_id" {
  description = "returns a string"
  value       = alicloud_ros_change_set.this.stack_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ros_change_set.this.status
}

output "timeout_in_minutes" {
  description = "returns a number"
  value       = alicloud_ros_change_set.this.timeout_in_minutes
}

output "this" {
  value = alicloud_ros_change_set.this
}
```

[top](#index)