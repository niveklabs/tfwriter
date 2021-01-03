# alicloud_oos_executions

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
module "alicloud_oos_executions" {
  source = "./modules/alicloud/d/alicloud_oos_executions"

  # category - (optional) is a type of string
  category = null
  # end_date - (optional) is a type of string
  end_date = null
  # end_date_after - (optional) is a type of string
  end_date_after = null
  # executed_by - (optional) is a type of string
  executed_by = null
  # ids - (optional) is a type of list of string
  ids = []
  # include_child_execution - (optional) is a type of bool
  include_child_execution = null
  # mode - (optional) is a type of string
  mode = null
  # output_file - (optional) is a type of string
  output_file = null
  # parent_execution_id - (optional) is a type of string
  parent_execution_id = null
  # ram_role - (optional) is a type of string
  ram_role = null
  # sort_field - (optional) is a type of string
  sort_field = null
  # sort_order - (optional) is a type of string
  sort_order = null
  # start_date_after - (optional) is a type of string
  start_date_after = null
  # start_date_before - (optional) is a type of string
  start_date_before = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_name - (optional) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_date_after" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "executed_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "include_child_execution" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_execution_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ram_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_field" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_order" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_date_after" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_date_before" {
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

variable "template_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_oos_executions" "this" {
  category                = var.category
  end_date                = var.end_date
  end_date_after          = var.end_date_after
  executed_by             = var.executed_by
  ids                     = var.ids
  include_child_execution = var.include_child_execution
  mode                    = var.mode
  output_file             = var.output_file
  parent_execution_id     = var.parent_execution_id
  ram_role                = var.ram_role
  sort_field              = var.sort_field
  sort_order              = var.sort_order
  start_date_after        = var.start_date_after
  start_date_before       = var.start_date_before
  status                  = var.status
  tags                    = var.tags
  template_name           = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "executions" {
  description = "returns a list of object"
  value       = data.alicloud_oos_executions.this.executions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_oos_executions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_oos_executions.this.ids
}

output "this" {
  value = alicloud_oos_executions.this
}
```

[top](#index)