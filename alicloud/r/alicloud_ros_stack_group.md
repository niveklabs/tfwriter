# alicloud_ros_stack_group

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
module "alicloud_ros_stack_group" {
  source = "./modules/alicloud/r/alicloud_ros_stack_group"

  # account_ids - (optional) is a type of string
  account_ids = null
  # administration_role_name - (optional) is a type of string
  administration_role_name = null
  # description - (optional) is a type of string
  description = null
  # execution_role_name - (optional) is a type of string
  execution_role_name = null
  # operation_description - (optional) is a type of string
  operation_description = null
  # operation_preferences - (optional) is a type of string
  operation_preferences = null
  # region_ids - (optional) is a type of string
  region_ids = null
  # stack_group_name - (required) is a type of string
  stack_group_name = null
  # template_body - (optional) is a type of string
  template_body = null
  # template_url - (optional) is a type of string
  template_url = null
  # template_version - (optional) is a type of string
  template_version = null

  parameters = [{
    parameter_key   = null
    parameter_value = null
  }]

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_ids" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "administration_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "execution_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operation_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operation_preferences" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_ids" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_group_name" {
  description = "(required)"
  type        = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ros_stack_group" "this" {
  # account_ids - (optional) is a type of string
  account_ids = var.account_ids
  # administration_role_name - (optional) is a type of string
  administration_role_name = var.administration_role_name
  # description - (optional) is a type of string
  description = var.description
  # execution_role_name - (optional) is a type of string
  execution_role_name = var.execution_role_name
  # operation_description - (optional) is a type of string
  operation_description = var.operation_description
  # operation_preferences - (optional) is a type of string
  operation_preferences = var.operation_preferences
  # region_ids - (optional) is a type of string
  region_ids = var.region_ids
  # stack_group_name - (required) is a type of string
  stack_group_name = var.stack_group_name
  # template_body - (optional) is a type of string
  template_body = var.template_body
  # template_url - (optional) is a type of string
  template_url = var.template_url
  # template_version - (optional) is a type of string
  template_version = var.template_version

  dynamic "parameters" {
    for_each = var.parameters
    content {
      # parameter_key - (optional) is a type of string
      parameter_key = parameters.value["parameter_key"]
      # parameter_value - (optional) is a type of string
      parameter_value = parameters.value["parameter_value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "administration_role_name" {
  description = "returns a string"
  value       = alicloud_ros_stack_group.this.administration_role_name
}

output "execution_role_name" {
  description = "returns a string"
  value       = alicloud_ros_stack_group.this.execution_role_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_ros_stack_group.this.id
}

output "stack_group_id" {
  description = "returns a string"
  value       = alicloud_ros_stack_group.this.stack_group_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ros_stack_group.this.status
}

output "this" {
  value = alicloud_ros_stack_group.this
}
```

[top](#index)