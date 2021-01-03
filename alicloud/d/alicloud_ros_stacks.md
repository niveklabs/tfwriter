# alicloud_ros_stacks

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_ros_stacks" {
  source = "./modules/alicloud/d/alicloud_ros_stacks"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # parent_stack_id - (optional) is a type of string
  parent_stack_id = null
  # show_nested_stack - (optional) is a type of bool
  show_nested_stack = null
  # stack_name - (optional) is a type of string
  stack_name = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_stack_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "show_nested_stack" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "stack_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ros_stacks" "this" {
  enable_details    = var.enable_details
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  parent_stack_id   = var.parent_stack_id
  show_nested_stack = var.show_nested_stack
  stack_name        = var.stack_name
  status            = var.status
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ros_stacks.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ros_stacks.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ros_stacks.this.names
}

output "stacks" {
  description = "returns a list of object"
  value       = data.alicloud_ros_stacks.this.stacks
}

output "this" {
  value = alicloud_ros_stacks.this
}
```

[top](#index)