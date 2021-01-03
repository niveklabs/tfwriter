# alicloud_ros_stack

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ros_stack" {
  source = "./modules/alicloud/r/alicloud_ros_stack"

  # create_option - (optional) is a type of string
  create_option = null
  # deletion_protection - (optional) is a type of string
  deletion_protection = null
  # disable_rollback - (optional) is a type of bool
  disable_rollback = null
  # notification_urls - (optional) is a type of set of string
  notification_urls = []
  # ram_role_name - (optional) is a type of string
  ram_role_name = null
  # replacement_option - (optional) is a type of string
  replacement_option = null
  # retain_all_resources - (optional) is a type of bool
  retain_all_resources = null
  # retain_resources - (optional) is a type of set of string
  retain_resources = []
  # stack_name - (required) is a type of string
  stack_name = null
  # stack_policy_body - (optional) is a type of string
  stack_policy_body = null
  # stack_policy_during_update_body - (optional) is a type of string
  stack_policy_during_update_body = null
  # stack_policy_during_update_url - (optional) is a type of string
  stack_policy_during_update_url = null
  # stack_policy_url - (optional) is a type of string
  stack_policy_url = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_body - (optional) is a type of string
  template_body = null
  # template_url - (optional) is a type of string
  template_url = null
  # template_version - (optional) is a type of string
  template_version = null
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
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "create_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_protection" {
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

variable "retain_all_resources" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "retain_resources" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "stack_name" {
  description = "(required)"
  type        = string
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
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

variable "template_version" {
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
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ros_stack" "this" {
  create_option                   = var.create_option
  deletion_protection             = var.deletion_protection
  disable_rollback                = var.disable_rollback
  notification_urls               = var.notification_urls
  ram_role_name                   = var.ram_role_name
  replacement_option              = var.replacement_option
  retain_all_resources            = var.retain_all_resources
  retain_resources                = var.retain_resources
  stack_name                      = var.stack_name
  stack_policy_body               = var.stack_policy_body
  stack_policy_during_update_body = var.stack_policy_during_update_body
  stack_policy_during_update_url  = var.stack_policy_during_update_url
  stack_policy_url                = var.stack_policy_url
  tags                            = var.tags
  template_body                   = var.template_body
  template_url                    = var.template_url
  template_version                = var.template_version
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
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ros_stack.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ros_stack.this.status
}

output "this" {
  value = alicloud_ros_stack.this
}
```

[top](#index)