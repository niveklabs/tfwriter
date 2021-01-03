# alicloud_oos_execution

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
module "alicloud_oos_execution" {
  source = "./modules/alicloud/r/alicloud_oos_execution"

  # description - (optional) is a type of string
  description = null
  # loop_mode - (optional) is a type of string
  loop_mode = null
  # mode - (optional) is a type of string
  mode = null
  # parameters - (optional) is a type of string
  parameters = null
  # parent_execution_id - (optional) is a type of string
  parent_execution_id = null
  # safety_check - (optional) is a type of string
  safety_check = null
  # template_name - (required) is a type of string
  template_name = null
  # template_version - (optional) is a type of string
  template_version = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "loop_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_execution_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "safety_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "template_version" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "alicloud_oos_execution" "this" {
  description         = var.description
  loop_mode           = var.loop_mode
  mode                = var.mode
  parameters          = var.parameters
  parent_execution_id = var.parent_execution_id
  safety_check        = var.safety_check
  template_name       = var.template_name
  template_version    = var.template_version

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
output "counters" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.counters
}

output "create_date" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.create_date
}

output "end_date" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.end_date
}

output "executed_by" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.executed_by
}

output "id" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.id
}

output "is_parent" {
  description = "returns a bool"
  value       = alicloud_oos_execution.this.is_parent
}

output "outputs" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.outputs
}

output "ram_role" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.ram_role
}

output "start_date" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.start_date
}

output "status" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.status
}

output "status_message" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.status_message
}

output "template_id" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.template_id
}

output "template_version" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.template_version
}

output "update_date" {
  description = "returns a string"
  value       = alicloud_oos_execution.this.update_date
}

output "this" {
  value = alicloud_oos_execution.this
}
```

[top](#index)