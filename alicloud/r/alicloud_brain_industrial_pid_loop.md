# alicloud_brain_industrial_pid_loop

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
module "alicloud_brain_industrial_pid_loop" {
  source = "./modules/alicloud/r/alicloud_brain_industrial_pid_loop"

  # pid_loop_configuration - (required) is a type of string
  pid_loop_configuration = null
  # pid_loop_dcs_type - (required) is a type of string
  pid_loop_dcs_type = null
  # pid_loop_desc - (optional) is a type of string
  pid_loop_desc = null
  # pid_loop_is_crucial - (required) is a type of bool
  pid_loop_is_crucial = null
  # pid_loop_name - (required) is a type of string
  pid_loop_name = null
  # pid_loop_type - (required) is a type of string
  pid_loop_type = null
  # pid_project_id - (required) is a type of string
  pid_project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "pid_loop_configuration" {
  description = "(required)"
  type        = string
}

variable "pid_loop_dcs_type" {
  description = "(required)"
  type        = string
}

variable "pid_loop_desc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pid_loop_is_crucial" {
  description = "(required)"
  type        = bool
}

variable "pid_loop_name" {
  description = "(required)"
  type        = string
}

variable "pid_loop_type" {
  description = "(required)"
  type        = string
}

variable "pid_project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_brain_industrial_pid_loop" "this" {
  pid_loop_configuration = var.pid_loop_configuration
  pid_loop_dcs_type      = var.pid_loop_dcs_type
  pid_loop_desc          = var.pid_loop_desc
  pid_loop_is_crucial    = var.pid_loop_is_crucial
  pid_loop_name          = var.pid_loop_name
  pid_loop_type          = var.pid_loop_type
  pid_project_id         = var.pid_project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_brain_industrial_pid_loop.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_brain_industrial_pid_loop.this.status
}

output "this" {
  value = alicloud_brain_industrial_pid_loop.this
}
```

[top](#index)