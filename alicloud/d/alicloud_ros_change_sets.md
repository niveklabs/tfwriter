# alicloud_ros_change_sets

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ros_change_sets" {
  source = "./modules/alicloud/d/alicloud_ros_change_sets"

  # change_set_name - (optional) is a type of string
  change_set_name = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # stack_id - (required) is a type of string
  stack_id = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "change_set_name" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "stack_id" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ros_change_sets" "this" {
  change_set_name = var.change_set_name
  enable_details  = var.enable_details
  ids             = var.ids
  name_regex      = var.name_regex
  output_file     = var.output_file
  stack_id        = var.stack_id
  status          = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ros_change_sets.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ros_change_sets.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ros_change_sets.this.names
}

output "sets" {
  description = "returns a list of object"
  value       = data.alicloud_ros_change_sets.this.sets
}

output "this" {
  value = alicloud_ros_change_sets.this
}
```

[top](#index)